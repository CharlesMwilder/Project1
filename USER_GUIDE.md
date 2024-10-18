# Documentation pour les utilisateurs

## Utilisation de base: 

### Comment utiliser **TightVNC**

1. Vérifier que Tightvnc est bien fonctionnel sur le serveur dans la barre des tâches
 
![Serveur capture ](https://github.com/user-attachments/assets/b39a7e9b-3a9e-4367-a67e-f70e15b8847e) 

2. Ouverture de Tightvnc sur le client

![Capture d'écran 2024-10-16 145524](https://github.com/user-attachments/assets/e5de72de-6a55-4025-adcf-cba1c77def5b)

3. Indiquer l'adresse ip du serveur

![Capture d'écran 2024-10-16 145644](https://github.com/user-attachments/assets/a3528194-b3b6-40f1-b0f2-1943561f06e1)

4. TightVNC demande le mot de passe du serveur
 
![Capture d’écran 2024-10-16 à 16 30 44](https://github.com/user-attachments/assets/2163b395-5039-41fe-9c30-303ce078f380)

5. Insertion du mot de passe

![Capture d’écran 2024-10-16 à 16 32 01](https://github.com/user-attachments/assets/bc291968-5493-446a-ac1e-920f1c230cea)

6. Connexion etablie entre le client et le serveur

![Capture d’écran 2024-10-16 à 16 12 02](https://github.com/user-attachments/assets/9f6ba006-abf2-44fe-bb40-9eb7a23832d1)



### Comment utiliser **Connexion Bureau à Distance**

1. (Depuis le client) Cliquez sur Demarrer, recherchez le programme et lancez le en cliquant dessus

![Capture d'écran 2024-10-11 1100212](https://github.com/user-attachments/assets/d08ba675-779f-4de2-9fd7-7dc79cc5fe04)

2. Indiquer l'adresse IP du serveur, puis cliquer sur _**Connecter**_

![Capture d'écran 2024-10-11 1100492](https://github.com/user-attachments/assets/5f54e1c3-23e4-4118-8da8-ae7ed26fdd21)

3. Insertion du mot de passe du serveur, puis cliquez sur _**OK**_

![Capture d'écran 2024-10-11 1101282](https://github.com/user-attachments/assets/36b0cb17-13dd-4f6d-922c-244a15eb5aa9)

4. (Depuis le serveur) Cette fenetre va apparaitre, qui va permettre d'autoriser le client à se connecter au serveur

![Capture d'écran 2024-10-11 1101402](https://github.com/user-attachments/assets/a8f05f3b-1b79-4e3d-961d-b5f380d7b347)


5. Connexion etablie entre le client et le serveur
   
![Capture d'écran 2024-10-17 115704](https://github.com/user-attachments/assets/e39195ad-5e79-4c0f-8575-5bee96fedf42)



## Utilisation avancée : comment utiliser au mieux les options


Ce guide vous expliquera comment activer le Bureau à Distance et configurer l'authentification au niveau du réseau (NLA) sur vos systèmes Windows (serveur et client), modifier un script, et configurer les règles de pare-feu nécessaires.

---

## Prérequis

- Accès administratif au serveur Windows.
- Accès à PowerShell avec les privilèges nécessaires.
- Des captures d'écran sont fournies pour vous guider visuellement.

---

## Configuration de la Politique d'Exécution de PowerShell sur RemoteSigned pour le **Client** et le **Serveur**

### Étape 1 : Ouvrir PowerShell en Tant qu'Administrateur

1. Ouvrez la barre de recherche, tapez **PowerShell**, puis faites un clic droit et sélectionnez **Exécuter en tant qu'administrateur**.
   
   ![SRV PS](https://github.com/user-attachments/assets/60aac6d7-ef35-45b8-8cd2-394dd8be5c69)

### Étape 2 : Définir la Politique d'Exécution sur RemoteSigned

1. Entrez la commande suivante dans PowerShell :

   ```powershell
   Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
   ```

2. Si vous recevez une demande de confirmation, tapez **Y** et appuyez sur **Entrée**.

---

## Script pour Activer le Bureau à Distance et l'Authentification au Niveau Réseau (NLA) **ou** TightVNC sur le Serveur Windows

### Étape 1 : Créer le Script PowerShell

1. Ouvrez **Notepad** sur votre serveur.
   
   ![SRV Notepad](https://github.com/user-attachments/assets/a3b474e6-8d69-4cbc-bd43-fe740a505b00)

2. a. Pour le Bureau à Distance, copiez et collez le script suivant dans le fichier :

   ```powershell
   # Activer le Bureau à Distance et NLA
   Write-Host "Activation du Bureau à Distance..."

   Set-ItemProperty -Path 'HKLM:\System\CurrentControlSet\Control\Terminal Server' -Name "fDenyTSConnections" -Value 0
   Set-ItemProperty -Path 'HKLM:\System\CurrentControlSet\Control\Terminal Server\WinStations\RDP-Tcp' -Name "UserAuthentication" -Value 1

   # Ajouter une règle de pare-feu pour autoriser le Bureau à Distance via Windows Defender
   Write-Host "Configuration du pare-feu pour autoriser le Bureau à Distance..."

   Enable-NetFirewallRule -DisplayGroup "Remote Desktop"

   Write-Host "Configuration du Bureau à Distance terminée."
   ```
![SRV Script Paste](https://github.com/user-attachments/assets/79d2b090-e7a1-4b5c-bc90-98522fa759c3)

2. b. Et pour TightVNC
```powershell
Write-Host "Starting TightVNC Server..."
Start-Process "C:\Program Files\TightVNC\tvnserver.exe" -ArgumentList '-run'
```

3. Enregistrez le fichier sous le nom `EnableRemoteDesktop.ps1` ou `StartTightVNC.ps1`en allant dans **File** > **Save As**.
   
   ![SRV Save Folder ps1](https://github.com/user-attachments/assets/1626d7cb-fc41-4492-ac44-3613600db84a)

---

### Étape 2 : Exécuter le Script

1. Faites un clic droit sur `EnableRemoteDesktop.ps1` ou `StartTightVNC.ps1`et sélectionnez **Run with PowerShell**.

2. Si une demande d'autorisation apparaît, tapez **Y** pour confirmer et appuyez sur **Entrée**. Le script sera exécuté avec succès sur le serveur !

---

## Script pour Activer la Connexion à Distance ou TightVNC Viewer sur le Client Windows

### Étape 1 : Créer le Script PowerShell sur le Client

1. Ouvrez **Notepad** sur le client.

2. b. Pour Connexion à distance, collez la commande suivante dans le fichier :

   ```powershell
   Start-Process "mstsc" "/v:192.168.0.100"
   ```
2. a. Et pour TightVNC, collez la commande suivante :
   ```powershell
   Start-Process "C:\Program Files\TightVNC\tvnviewer.exe"
   ```
   
3. Enregistrez le fichier sous le nom `ConnexionDistance.ps1`.


## Étape 2 : Répétez l'étape 2 précédente avec votre nouveau script.

1. Done !

# Explication du script

## Script de démarrage rapide du serveur TightVNC

Ce script démarre le serveur TightVNC sur une machine Windows en utilisant `Start-Process` et affiche un message en utilisant `Write-Host`.


---

## FAQ : solutions aux problèmes connus et courants liés à l’utilisation

 
