# Documentation pour les administrateurs  

## 1. Prérequis techniques  
**TightVNC:**
- Windows (7, 8, 10, Server 2008/2012/2016)
- Processeur : Processeur compatible x86 (Intel ou AMD)
- Mémoire RAM : Minimum 512 Mo de RAM (1 Go recommandé)
- Espace disque : Environ 20 Mo pour l'installation
- Accès réseau entre la machine cliente et la machine hôte pour la connexion à distance

**Connexion Bureau à Distance de Windows:**
- Disponible uniquement sur les éditions Pro & Enterprise
- Windows 7, 8, 8.1, 10, 11, Windows Server 2008/2012/2016/2019
- Processeur : Processeur compatible x86/x64 (Intel ou AMD)
- Mémoire RAM : 2 Go minimum (4 Go recommandés pour de meilleures performances)
- Espace disque : 200 Mo pour les fichiers temporaires du service Remote Desktop
- Accès réseau entre la machine cliente et la machine hôte pour la connexion à distance
  
## 2. Étapes d'installation et de configuration : instruction étape par étape  

 - ### Configuration du nom du serveur et du client


- ### Configuration de l'adresse IP du server et du client

1. **Accéder aux paramètres réseau** : cliquer avec le bouton droit sur l'icône réseau dans la barre des tâches et sélectionner "Ouvrir les paramètres de réseau et Internet"  

![Capture d'écran 2024-10-09 145145](https://github.com/user-attachments/assets/5f67d344-28e7-4bb4-9286-44efdbaedaf2)  

2. **Modifier les options de l'adaptateur** : Cliquer sur "Modifier les options de l’adaptateur"  

![Capture d'écran 2024-10-09 145216](https://github.com/user-attachments/assets/a197f3d6-3315-4e4a-9bb1-86424bc77663)  

3. **Sélectionner l'adaptateur** : Faire un clic droit sur l'adaptateur réseau utilisé (par exemple, Ethernet) et sélectionner "Propriété"  

![Capture d'écran 2024-10-09 145241](https://github.com/user-attachments/assets/f1a1f02f-42b1-48e5-affd-734f29c8452b)  

4. **Protocole Internet Version 4 (TCP/IPv4)** : Dans la liste, sélectionner "Protocole Internet Version 4 (TCP/IPv4)" et cliquer sur "Propriétés"  

![Capture d'écran 2024-10-09 145342](https://github.com/user-attachments/assets/d272398f-9886-4b99-9c4c-c21f872360c4)  

5. **Configurer l'adresse IP** : Sélectionner "Utiliser l'adresse IP suivante", entrer l'adresse IP puis le masque et cliquer sur "Ok" pour valider
 
   (image de droite: Serveur)  (image de gauche: Client)
   
![Capture d'écran 2024-10-09 145843](https://github.com/user-attachments/assets/01c459e4-3b14-420e-938a-71821ce33aa5)
![Capture d'écran 2024-10-09 150533](https://github.com/user-attachments/assets/86b594fe-b2b1-4a5a-ab91-337e3e50e871)  

7. **Vérification avec le panneau d'invite des commandes**: Executer ```ipconfig``` pour vérifier que l'addresse IP à bien été modifié  

![Capture d'écran 2024-10-09 150244](https://github.com/user-attachments/assets/781acd18-0ff3-4ea9-bb32-6054a90f4418)
![Capture d'écran 2024-10-09 150715](https://github.com/user-attachments/assets/ecadb46f-5baf-464b-b446-eeaf6a01d70f)


- ### Installation de la version TightVNCserver sur le serveur
1. **Télécharger le Logiciel TightVNC**: Aller sur le site web de [TightVNC](https://www.tightvnc.com/download.php) et télecharger le logiciel

<img width="522" alt="1 " src="https://github.com/user-attachments/assets/9c4f1e71-1133-4a2f-90c4-c66b02ef7b89">  

2. **Executer le logiciel**
  
3. **Choisir le type de configuration**: Selectionner "Custom" et cliquer sur "Next"  

![Capture d'écran 2024-10-09 161718](https://github.com/user-attachments/assets/b264c6bc-265b-48ac-8881-44e4c2ab1dda)  

4. **Configuration Custom**: Faire un clic droit sur  "TightVNC Viewer" et Cliquer sur "Entire feature will be unavailable" (Cela permet d'installer seulement la version server) . Un croix rouge doit apparaitre devant TightVNC Viewer 

![Capture d'écran 2024-10-09 161741-2](https://github.com/user-attachments/assets/9866444c-81ea-488a-b5aa-8af3b65636af)  
Une croix rouge doit apparaitre devant TightVNC Viewer  
![Capture d'écran 2024-10-09 161756-2](https://github.com/user-attachments/assets/f6e979fb-c57c-4c6a-8299-0cbfa3d24911)  

5. **Sélectionner les tâches additionnelles**: Cocher "Register TightVNC Server as a stystem service " et "Configure system to allow services simluate Ctrl-Alt-Del". Laisser décocher "Run only as a system service, disable user application mode"
![Capture d'écran 2024-10-09 162116](https://github.com/user-attachments/assets/54fd87d0-d025-4cec-bc48-284ebb8d3f90)


6. **Configuration sécuriser des mots de passe**: Créer 2 mots de passe différents pour l'administrateur et le client à distance. Pour le client à distance, sélectionner "require password-based authentication" et rentrer le mot de passe choisi. Pour l'administrateur, sélectionner "protect control interface with an administrative password" et rentrer un mot de passe différent.

![Capture d'écran 2024-10-09 170435](https://github.com/user-attachments/assets/4afab5f9-a941-474b-ad24-333128cca703)

Remarque: Il est conseillé de suivre les préconisations de [création d'un mot de passe fort et sécurisé]( https://support.microsoft.com/fr-fr/windows/cr%C3%A9er-et-utiliser-un-mot-de-passe-fort-c5cebb49-8c53-4f5e-2bc4-fe357ca048eb#:~:text=La%20s%C3%A9curit%C3%A9%20du%20mot%20de,%2C%20minuscules%2C%20chiffres%20et%20symboles.) par Microsoft 

7. **Fin de l'installation**: cliquer sur "Finish" pour terminer l'installation

![Capture d'écran 2024-10-09 170443](https://github.com/user-attachments/assets/d5912d77-d0d4-4cf2-9873-fbea691f4431)  

- ### Installation de la version TightVNCviewer sur le client à distance

1. Répéter à l'identique les 3 premières consignes de l'[installation de TightVNC sur le serveur](https://github.com/WildCodeSchool/TSSR-2409-P1-G2-Teleassistance/blob/main/INSTALL.md#installation-de-la-version-tightvncserver-sur-le-serveur)

- ### Configuration de la connexion Bureau à distance
  

## 3. FAQ : solutions aux problèmes connus et courants liés à l’installation et à la configuration  
