## Documentation pour les administrateurs  

### 1. Prérequis techniques  

### 2. Étapes d'installation et de configuration : instruction étape par étape  

- Configuration du nom du serveur et du client


- Configuration de l'adresse IP du server et du client

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


- Installation de la version TightVNCserver sur le serveur Windows 2022
1. Télécharger le Logiciel TightVNC

<img width="522" alt="1 " src="https://github.com/user-attachments/assets/9c4f1e71-1133-4a2f-90c4-c66b02ef7b89">  

2. Executer le logiciel
  
3. Choisir le type de configuration: Selectionner "Custom" et cliquer sur "Next"  
![Capture d'écran 2024-10-09 161718](https://github.com/user-attachments/assets/b264c6bc-265b-48ac-8881-44e4c2ab1dda)  

4. Configuration Custom: Faire un clic droit sur  "TightVNC Viewer" et Cliquer sur "Entire feature will be unavailable" (Cela permet d'installer seulement la version server) . Un croix rouge doit apparaitre devant TightVNC Viewer 
![Capture d'écran 2024-10-09 161741-2](https://github.com/user-attachments/assets/9866444c-81ea-488a-b5aa-8af3b65636af)  
Une croix rouge doit apparaitre devant TightVNC Viewer  
![Capture d'écran 2024-10-09 161756-2](https://github.com/user-attachments/assets/f6e979fb-c57c-4c6a-8299-0cbfa3d24911)  

5. Sélectionner les tâches additionnelles: Cocher "Register TightVNC Server as a stystem service " et "Configure system to allow services simluate Ctrl-Alt-Del". Laisser décocher "Run only as a system service, disable user application mode"
![Capture d'écran 2024-10-09 162116](https://github.com/user-attachments/assets/54fd87d0-d025-4cec-bc48-284ebb8d3f90)


6. Configuration des mots de passe
![Capture d'écran 2024-10-09 170435](https://github.com/user-attachments/assets/4afab5f9-a941-474b-ad24-333128cca703)
7.
![Capture d'écran 2024-10-09 170443](https://github.com/user-attachments/assets/d5912d77-d0d4-4cf2-9873-fbea691f4431)  

- Installation de la version TightVNCviewer sur le client Windows 10 Pro



- Configuration de la connexion Bureau à distance
  

### 3. FAQ : solutions aux problèmes connus et courants liés à l’installation et à la configuration  
