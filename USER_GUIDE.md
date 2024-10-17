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

Connexion etablie entre le client et le serveur

![Capture d’écran 2024-10-16 à 16 12 02](https://github.com/user-attachments/assets/9f6ba006-abf2-44fe-bb40-9eb7a23832d1)











## Utilisation de base :

### Comment utiliser **Connexion Bureau à Distance**

1. (Depuis le client) Cliquez sur Demarrer, recherchez le programme et lancez le en cliquant dessus

![Capture d'écran 2024-10-11 1100212](https://github.com/user-attachments/assets/d08ba675-779f-4de2-9fd7-7dc79cc5fe04)

2. Indiquer l'adresse IP du serveur, puis cliquer sur _**Connecter**_

![Capture d'écran 2024-10-11 1100492](https://github.com/user-attachments/assets/5f54e1c3-23e4-4118-8da8-ae7ed26fdd21)

3. Insertion du mot de passe du serveur, puis cliquez sur _**OK**_

![Capture d'écran 2024-10-11 1101282](https://github.com/user-attachments/assets/36b0cb17-13dd-4f6d-922c-244a15eb5aa9)

4. (Depuis le serveur) Cette fenetre va apparaitre, qui va permettre d'autoriser le client à se connecter au serveur

![Capture d'écran 2024-10-11 1101402](https://github.com/user-attachments/assets/a8f05f3b-1b79-4e3d-961d-b5f380d7b347)



## Utilisation avancée : comment utiliser au mieux les options

Ce guide vous aidera à activer le bureau à distance et à configurer l'authentification au niveau du réseau (NLA) sur votre serveur et client Windows, à modifier un script et à ajouter les règles de pare-feu nécessaires.

## Prérequis

- Serveur Windows avec des privilèges administratifs.
- Accès à PowerShell.
- Des captures d'écran sont fournies à titre d'aide visuelle.

---

## Définir la politique d'exécution de PowerShell à RemoteSigned pour le **CLIENT** et le **SERVEUR**

### Étape 1 : Ouvrir PowerShell en tant qu'administrateur 

1. Dans la barre de recherche, tapez PowerShell, cliquez avec le bouton droit de la souris et sélectionnez Exécuter en tant qu'administrateur.
![SRV PS](https://github.com/user-attachments/assets/60aac6d7-ef35-45b8-8cd2-394dd8be5c69)


### Étape 2 : Définir la politique d'exécution sur RemoteSigned

1. Entrez la commande suivante : ``` Set-ExecutionPolicy RemoteSigned -Scope CurrentUser ```

2. Après avoir exécuté la commande, il se peut que l'on vous demande de confirmer la modification. Vous pouvez répondre par :

Tapez Y pour confirmer et appuyez sur Entrée.

## Script pour l'Activation du bureau à distance et de l'authentification de niveau réseau (NLA) sur le serveur Windows

## Étape 1 : Créer le script PowerShell

1. Ouvrez **Notepad** sur votre serveur.
![SRV Notepad](https://github.com/user-attachments/assets/a3b474e6-8d69-4cbc-bd43-fe740a505b00)


2. Copiez et collez le script suivant dans le fichier :
![SRV Script Paste](https://github.com/user-attachments/assets/bbb7fe2e-952f-40ae-87d0-34ac13123885)


```powershell
   # Enable Remote Desktop and NLA
   Write-Host "Enabling Remote Desktop..."

   Set-ItemProperty -Path 'HKLM:\System\CurrentControlSet\Control\Terminal Server' -Name "fDenyTSConnections" -Value 0
   Set-ItemProperty -Path 'HKLM:\System\CurrentControlSet\Control\Terminal Server\WinStations\RDP-Tcp' -Name "UserAuthentication" -Value 1

   # Add a firewall rule to allow Remote Desktop (RDP) through Windows Defender Firewall
   Write-Host "Configuring firewall to allow Remote Desktop..."

   Enable-NetFirewallRule -DisplayGroup "Remote Desktop"

   Write-Host "Remote Assistance setup completed."
```

3. Enregistrez le fichier sous `EnableRemoteDesktop.ps1` en cliquant sur **File** > **Save As**.
![SRV Save Folder ps1](https://github.com/user-attachments/assets/1626d7cb-fc41-4492-ac44-3613600db84a)


## Étape 2 : Run le Script

1. Faites un clic droit sur `EnableRemoteDesktop.ps1` et cliquez sur « Run with PowerShell ».

2. Il peut vous demander si vous êtes sûr d'exécuter ce script, si c'est le cas, tapez : « y » et c'est fait pour le serveur !
 

## Script pour l'Activation du bureau à distance et de l'authentification de niveau réseau (NLA) sur le client Windows




---

- ## FAQ : solutions aux problèmes connus et courants liés à l’utilisation
 
