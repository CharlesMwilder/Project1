# Documentation générale

## 1. Présentation du projet, objectifs finaux  

**Objectifs finaux:**
- Objectif principal: Configurer un accès sécurisé pour faire de la téléassistance sur un serveur depuis un client en utilsant le logiciel TightVNC et Connexion Bureau à Distance de Windows  
- Objectif secondaire: Script PowerShell pour faciliter la connexion initiale de la téléassistance  

## 2. Introduction : mise en contexte
Le serveur a rencontré un probleme qu'il n'arrivait pas à resoudre. Le client a dû intervenir sur la machine du serveur en se connectant à distance avec TightVNC et Bureau Connexion à Distance de Windows.

## 3. Membres du groupe de projet (rôles par sprint)

|   | Sprint S1 | Sprint S2 |  
| :--: | :-------: | :-------: |
| SCRUM MASTER | Charles | Mohammed |  
| PRODUCT OWNER | Igor | Camille |  
| TECHNICIANS | Mohammed et Camille | Charles et Igor |   

\
**Objectifs Sprint 2:**  
- Finaliser la documentation
- Réaliser les scripts pour la connexion à distance avec TightVNC  

| Membre | Tâches de chacun lors du Sprint 2 |
| :--: | :-------: |
| Mohammed | Documentation de l'utilisation de TightVNC sur le USER_GUIDE.md |
| Charles | Réalisation des scripts TightVNC + Documentation liée aux Scripts dans INSTALL.md et USER_GUIDE.md|
| Camille | Documentation de la partie installation dans INSTALL.md + Documentation du README.md |
| Igor | Documentation des pré-requis technique dans INSTALL.md + Documentation du REAME.md + Documentation User_GUIDE.md|

## 4. Choix techniques:

- Server:  
Windows Server 2022  
Nom : SRVWIN01  
Compte : Administrator
Mot de passe : Azerty1*  
Adresse IP fixe : 172.16.10.10/24  

- Client: 
Windows 10 Pro  
Nom : CLIWIN01  
Compte utilisateur : wilder 
Mot de passe : Azerty1*  
Adresse IP fixe : 172.16.10.20/24  

## 5. Difficultés rencontrées : problèmes techniques rencontrés
- Problème lors de la connexion de tightVNCviewer au serveur à distance:  
Message d'erreur: Password unset

- Problème lié à la configuration réseau sur virtualbox: Perte de la connexion après la configuration manuelle des IP sur notre client et serveur

## 6. Solutions trouvées : Solutions et alternatives trouvées
- Dans le panneau de configuration de TightVNCserver: reconfiguration du mot de passe pour l'accès à distance  

<img width="400" alt="Capture d'écran 2024-10-10 145844 - Copie" src="https://github.com/user-attachments/assets/65e3f8bd-1191-4bfa-9f45-7beeede38ebc">

- Sur virtualbox, il faut passer les machines virtuelles de la connexion NAT (par défaut) à la connexion en accès par pont pour permettre la connexion entre nos 2 VM.

![Capture d'écran 2024-10-15 123023](https://github.com/user-attachments/assets/3941faf1-d04c-451a-9946-e90bb4fad92e)


## 7. Améliorations possibles : suggestions d’améliorations futures

- Etablir une connexion entre un client et un seveur sur 2 réseaux différents via la redirection de port

