# Documentation pour les administrateurs  

## SOMMAIRE
- [1. Prérequis techniques](https://github.com/WildCodeSchool/TSSR-2409-P1-G2-Teleassistance/blob/main/INSTALL.md#one-pr%C3%A9requis-techniques)
- [2. Étapes d'installation et de configuration de TightVNC](https://github.com/WildCodeSchool/TSSR-2409-P1-G2-Teleassistance/blob/main/INSTALL.md#2%EF%B8%8F%E2%83%A3-%C3%A9tapes-dinstallation-et-de-configuration)
- [3. Étapes de configuration de Connexion Bureau à Distance de Windows](https://github.com/WildCodeSchool/TSSR-2409-P1-G2-Teleassistance/blob/main/INSTALL.md#3%EF%B8%8F%E2%83%A3-configuration-de-la-connexion-bureau-%C3%A0-distance)
- [4. Explication des Scripts](https://github.com/WildCodeSchool/TSSR-2409-P1-G2-Teleassistance/blob/main/INSTALL.md#4%EF%B8%8F%E2%83%A3-explication-des-scripts)
  
## :one: Prérequis techniques  

**TightVNC:**
- Windows (7, 8, 10, 11, Server 2008/2012/2016/2022)
- CPU: compatible x86 (Intel ou AMD)
- RAM: Minimum 512 Mo de RAM (1 Go recommandé)
- Stockage: Environ 20 Mo pour l'installation
- Accès réseau entre la machine cliente et la machine hôte pour la connexion à distance

**Connexion Bureau à Distance de Windows:**
- Disponible uniquement sur les éditions Pro & Enterprise
- Windows 7, 8, 8.1, 10, 11, Windows Server 2008/2012/2016/2019/2022
- CPU: compatible x86/x64 (Intel ou AMD)
- RAM: 2 Go minimum (4 Go recommandés pour de meilleures performances)
- Stockage: 200 Mo pour les fichiers temporaires du service Remote Desktop
- Accès réseau entre la machine cliente et la machine hôte pour la connexion à distance
  
## 2️⃣ Étapes d'installation et de configuration:  

- ### Configuration de l'adresse IP du server et du client

1. **Accéder aux paramètres réseau** : Cliquer avec le bouton droit sur l'icône réseau dans la barre des tâches et sélectionner "Ouvrir les paramètres de réseau et Internet"  

![Capture d'écran 2024-10-09 145145](https://github.com/user-attachments/assets/5f67d344-28e7-4bb4-9286-44efdbaedaf2)  

2. **Modifier les options de l'adaptateur** : Cliquer sur "Modifier les options de l’adaptateur"  

![Capture d'écran 2024-10-09 145216](https://github.com/user-attachments/assets/b1f0df44-118f-4d11-b770-89bbc2a0fdb6)  

3. **Sélectionner l'adaptateur** : Faire un clic droit sur l'adaptateur réseau utilisé (par exemple, Ethernet) et sélectionner "Propriété"  

![Capture d'écran 2024-10-09 145241](https://github.com/user-attachments/assets/f1a1f02f-42b1-48e5-affd-734f29c8452b)  

4. **Protocole Internet Version 4 (TCP/IPv4)** : Dans la liste, sélectionner "Protocole Internet Version 4 (TCP/IPv4)" et cliquer sur "Propriétés"  

![Capture d'écran 2024-10-09 145342](https://github.com/user-attachments/assets/bd39615f-421e-413e-858b-0cd99baf3373)

5. **Configurer l'adresse IP** : Sélectionner "Utiliser l'adresse IP suivante", entrer l'adresse IP puis le masque et cliquer sur "Ok" pour valider
 
   (image de droite: Serveur)  (image de gauche: Client)
   
![Capture d'écran 2024-10-09 145843](https://github.com/user-attachments/assets/d9ec5452-2a01-4f71-847d-9814f76c1f68)
![Capture d'écran 2024-10-09 150533](https://github.com/user-attachments/assets/86b594fe-b2b1-4a5a-ab91-337e3e50e871)  

6. **Vérification avec le panneau d'invite des commandes**: Executer ```ipconfig``` pour vérifier que l'addresse IP à bien été modifié  

![Capture d'écran 2024-10-09 150244](https://github.com/user-attachments/assets/781acd18-0ff3-4ea9-bb32-6054a90f4418)
![Capture d'écran 2024-10-09 150715](https://github.com/user-attachments/assets/ecadb46f-5baf-464b-b446-eeaf6a01d70f)


- ### Installation de la version TightVNC Server sur le serveur
1. **Télécharger le Logiciel TightVNC**: Aller sur le site web de [TightVNC](https://www.tightvnc.com/download.php) et télecharger le logiciel

<img src="https://github.com/user-attachments/assets/8a160481-e75a-4fcb-a3ad-068db5ec2ad8" alt="drawing" width="700"/>  

\
2. **Débuter l'installation de TightVNC**: Exécuter TightVNC, la fenêtre "TightVNC Setup" doit apparaître puis cliquer sur "Next"   

![Capture d'écran 2024-10-09 155800](https://github.com/user-attachments/assets/b04a5bf7-b4ac-42c0-83bb-27c9774ef611)

3. **Condition d'utilisation**: Lire les conditions d'utilisation, cocher la case "i accept the terms in the License Agreement" et cliquer sur "Next"

![Capture d'écran 2024-10-09 155933](https://github.com/user-attachments/assets/8f367a1b-a4a1-47b2-bac6-92556b5f4b07)

4. **Choisir le type de configuration**: Selectionner "Custom" et cliquer sur "Next"  

![Capture d'écran 2024-10-09 171353](https://github.com/user-attachments/assets/c07cf114-8c98-4d4b-8780-4e965c19d4b0)

5. **Configuration Custom**: Faire un clic droit sur  "TightVNC Viewer" et Cliquer sur "Entire feature will be unavailable" (Cela permet d'installer seulement la version server) . Un croix rouge doit apparaitre devant TightVNC Viewer 

![Capture d'écran 2024-10-09 161741-2](https://github.com/user-attachments/assets/711b0b9e-9987-4ca3-ae4f-e60fed306a35)  

Une croix rouge doit apparaitre devant TightVNC Viewer  

![Capture d'écran 2024-10-09 161756-2](https://github.com/user-attachments/assets/2df98ddf-9cc7-415b-9ed2-bb22735c096f)  

5. **Sélectionner les tâches additionnelles**: Cocher "Register TightVNC Server as a stystem service " et "Configure system to allow services simluate Ctrl-Alt-Del". Laisser décocher "Run only as a system service, disable user application mode"  

![Capture d'écran 2024-10-09 1621162](https://github.com/user-attachments/assets/9c824602-21b5-4553-a0c3-0594b325cacb)

6. **Lancer l'installation**: Cliquer sur le bouton "Install"  

![Capture d'écran 2024-10-09 171509](https://github.com/user-attachments/assets/824fd6de-5c66-4b1e-8471-976b21fc2634)

7. **Autoriser l'application TightVNC**: Cliquer sur "oui" pour autoriser l'application TightVNC Version 2.8.85 Installer, à effectuer des modifications sur votre appareil

![Capture d'écran 2024-10-09 171516v2](https://github.com/user-attachments/assets/82069485-c73e-4f97-baab-42eb0baf983b)

8. **Configuration sécuriser des mots de passe**: Créer 2 mots de passe différents pour l'administrateur et le client à distance. Pour le client à distance, sélectionner "require password-based authentication" et rentrer le mot de passe choisi. Pour l'administrateur, sélectionner "protect control interface with an administrative password" et rentrer un mot de passe différent.  

![Capture d'écran 2024-10-09 170435](https://github.com/user-attachments/assets/e013ad39-ac9f-439f-b9f4-249bbfec441b)

Remarque: Il est conseillé de suivre les préconisations de [création d'un mot de passe fort et sécurisé]( https://support.microsoft.com/fr-fr/windows/cr%C3%A9er-et-utiliser-un-mot-de-passe-fort-c5cebb49-8c53-4f5e-2bc4-fe357ca048eb#:~:text=La%20s%C3%A9curit%C3%A9%20du%20mot%20de,%2C%20minuscules%2C%20chiffres%20et%20symboles.) par Microsoft 

9. **Fin de l'installation**: cliquer sur "Finish" pour terminer l'installation

![Capture d'écran 2024-10-09 170443-2](https://github.com/user-attachments/assets/b617d9ae-81b3-4e27-b8e1-51d90306bf87)

## 2. Installation de la version TightVNC Viewer sur le client à distance

1. **Répéter à l'identique les 4 premières consignes de l'[installation de TightVNC sur le serveur](https://github.com/WildCodeSchool/TSSR-2409-P1-G2-Teleassistance/blob/main/INSTALL.md#installation-de-la-version-tightvncserver-sur-le-serveur)**  

2. **Configuration Custom**: Faire un clic droit sur "TightVNC Server" et cliquer sur "Entire feature will be unavailable". Vérifier la présence de la croix rouge devant TightVNC Server et cliquer sur "Next"  

\
<img src="https://github.com/user-attachments/assets/545b2885-9d76-4a4b-9181-3917157ea2a1" alt="drawing" width="500"/> 
<img src="https://github.com/user-attachments/assets/2bac9994-1441-41f8-8881-6d36b25b8a4b" alt="drawing" width="500"/>  

\
3. **Sélectionner les tâches additionnelles**: Cocher la case "Associate.vnc files with TightVNC Viewer" et cliquer sur "Next"  

![Capture d'écran 2024-10-09 171502](https://github.com/user-attachments/assets/826e3d3b-9e3e-4fd8-99b2-a2dd08810002)

4. **Lancer l'installation**: Cliquer sur le bouton "Install"  

![Capture d'écran 2024-10-09 171509](https://github.com/user-attachments/assets/824fd6de-5c66-4b1e-8471-976b21fc2634)

5. **autoriser l'application TightVNC**: Cliquer sur "oui" pour autoriser l'application TightVNC Version 2.8.85 Installer, à effectuer des modifications sur votre appareil  

![Capture d'écran 2024-10-09 171516v2](https://github.com/user-attachments/assets/c8251f90-3e23-41d5-8d64-9fb1c578b223)  

6. **Fin de l'installation**: Cliquer sur "Finish" pour terminer l'installation  

![Capture d'écran 2024-10-09 170443-2](https://github.com/user-attachments/assets/de77389e-f921-45ef-9f13-c86f6ee21933)

## 3️⃣ Configuration de la connexion Bureau à distance  

1. **Accéder aux paramètres de l'application This PC**: Tapper dans la barre de recherche de l'ordinateur "This PC", ensuite faire un clic droit sur l'application "This PC" et sélectionner "Properties"  

![Capture d'écran 2024-10-11 105757](https://github.com/user-attachments/assets/58813e98-b908-4dae-8b7e-8dfc670937fa)

2. **Modifier les options de connexion à distance**: Cliquer sur "Remote desktop" qui se trouve dans "Related settings"  

![Capture d'écran 2024-10-11 1058212](https://github.com/user-attachments/assets/9dd778ae-9780-4d62-a4ee-a5e3fc4f95c4)

3. **Activer la connexion à distance**: Passer l'état d'"Enable Remote Desktop" de **Off** à **On** puis dans la fenêtre "Remote Desktop Settings" cliquer sur "confirm"  

![Capture d'écran 2024-10-16 160837](https://github.com/user-attachments/assets/3c74c435-e528-4071-90dd-eb6dac1c7f22)
![Capture d'écran 2024-10-16 160905](https://github.com/user-attachments/assets/f826e6fa-2685-4161-865d-23581bf54e56)

4. **Modifier les paramètres avancés**: Cliquer sur "Advances settings"  

![Capture d'écran 2024-10-16 161131](https://github.com/user-attachments/assets/fcd9712c-bcbf-4c7d-9d5f-528f6b994df1)

5. **Finaliser en sécurisant la connexion**: Activer l'option "Require computers to use Network Level Authentication to connect"  

![Capture d'écran 2024-10-11 105906](https://github.com/user-attachments/assets/147b709f-3aa2-482f-8cfd-3cd3f8dc5b9e)


## 4️⃣ Explication des scripts

### - Script pour le serveur Connexion Bureau à Distance

Ce script active le bureau à distance et l'authentification au niveau du réseau (NLA) sur un serveur Windows et configure le pare-feu pour qu'il autorise les connexions au bureau à distance.

#### Étapes du script :

1. **Activer le Bureau à distance** :
   ```powershell
    Write-Host "Enabling Remote Desktop..."
    Set-ItemProperty -Path 'HKLM:\System\CurrentControlSet\Control\Terminal Server' -Name "fDenyTSConnections" -Value 0
    Set-ItemProperty -Path 'HKLM:\System\CurrentControlSet\Control\Terminal Server\WinStations\RDP-Tcp' -Name "UserAuthentication" -Value 1
   ```

    - **fDenyTSConnections** : Cette propriété détermine si les connexions au bureau à distance sont autorisées. La valeur `0` désactive le refus des connexions, ce qui permet d'activer le bureau à distance.
    - **UserAuthentication** : Cette propriété active l'authentification au niveau du réseau (NLA) lorsqu'elle est réglée sur 1, ce qui oblige les utilisateurs à s'authentifier avant d'accéder au serveur via le bureau à distance.
      
2. **Ajouter une règle de pare-feu pour autoriser le bureau à distance** :
    ```powershell
    Write-Host "Configuring firewall to allow Remote Desktop..."
    Enable-NetFirewallRule -DisplayGroup "Remote Desktop"
    ```
    - **Enable-NetFirewallRule** : Cette cmdlet active les règles de pare-feu spécifiées par le `DisplayGroup`. 
    - **DisplayGroup : « Remote Desktop « ** : Fait référence à un ensemble prédéfini de règles de pare-feu qui autorisent les connexions Bureau à distance. L'activation de ce groupe garantit que les ports et les protocoles nécessaires sont autorisés à travers le pare-feu.

#### Explication des commandes

##### 1. **Modifications du registre** :
   Le script modifie le registre Windows pour activer Connexion Bureau à Distance:
   - **Registry Path** : `HKLM:\NSystem\NCurrentControlSet\NControl\NTerminal Server`
     - `HKLM` signifie **HKEY_LOCAL_MACHINE**, une ruche de registre qui contient les paramètres de l'ensemble de la machine.
   - **Property Name** : `fDenyTSConnections`
     - Contrôle si les connexions à Connexion Bureau à Distance sont refusées (`0` pour autoriser les connexions).
   - Nom de la propriété** : `UserAuthentication` (authentification de l'utilisateur)
     - Active NLA (`1`), obligeant les utilisateurs à s'authentifier avant de se connecter à Connexion Bureau à Distance.

##### 2. **Configuration du pare-feu** :
   - La cmdlet **Enable-NetFirewallRule** active les règles de pare-feu existantes. Dans ce cas, le groupe d'affichage `Remote Desktop` est utilisé pour autoriser les connexions Remote Desktop à travers le pare-feu Windows Defender.

### - Script de démarrage rapide du serveur TightVNC

Ce script démarre le serveur TightVNC sur une machine Windows en utilisant `Start-Process` et affiche un message en utilisant `Write-Host`.

#### Script:
```powershell
Write-Host "Starting TightVNC Server..."
Start-Process "C:\Program Files\TightVNC\tvnserver.exe" -ArgumentList '-run'
```
- **Write-Host** : Cette cmdlet affiche un message dans la console PowerShell. Ici, elle notifie que le serveur TightVNC est en train de démarrer.
- **Start-Process** : Cette cmdlet démarre le processus du serveur TightVNC. Le chemin d'accès pointe vers l'exécutable TightVNC, et la liste d'arguments '-run' garantit que le serveur est démarré en arrière-plan.


### - Script pour le client Conexion Bureau à Distance

Ce script utilise la cmdlet `Start-Process` pour ouvrir rapidement le client Connexion Bureau à Distance et se connecter à un serveur spécifié par IP.

#### Script :
```powershell
Start-Process « mstsc » « /v:172.16.10.10 »
```
- **Démarrer un processus** : Cette cmdlet démarre un processus sur l'ordinateur local. Dans ce cas, elle ouvre le client de connexion au bureau à distance (`mstsc`).
- **« /v:172.16.10.10 »** : Ce paramètre spécifie l'adresse IP du serveur auquel vous souhaitez vous connecter via Remote Desktop. Remplacez `172.16.10.10` par l'adresse IP de votre serveur si différent.

### - Script de démarrage rapide de TightVNC Viewer

Ce script démarre le « TightVNC viewer » sur le client Windows en utilisant `Start-Process`.

### Script:
```powershell
Start-Process "C:\Program Files\TightVNC\tvnviewer.exe"
```
- **Start-Process**: Cette cmdlet lance le processus TightVNC Viewer. Le chemin d'accès pointe vers l'exécutable TightVNC qui lance le Viewer.
