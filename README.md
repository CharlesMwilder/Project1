# TSSR-2409-P1-G2-Teleassistance

## Documentation générale

- ##### Présentation du projet, objectifs finaux

**Objectifs finaux:**
1. Configurer un accès sécurisé pour faire de la téléassistance sur un serveur depuis un client en utilsant le TightVNC et la connexion Bureau à distance de Windows
2. Script PS pour faciliter la connexion initiale de la téléassistance

- ##### Introduction : mise en contexte




- ##### Membres du groupe de projet (rôles par sprint)

Sprint 1ère semaine:  
Scrum master: Charles  
PO: Igor  

  
- ##### Choix techniques : quel OS, quelle version, etc.

- Server:
Windows Server 2022
Nom : SRVWIN01
Compte : Administrator (dans le groupe des admins locaux)
Mot de passe : Azerty1*
Adresse IP fixe : 172.16.10.10/24

- Client: 
Windows 10 Pro
Nom : CLIWIN01
Compte utilisateur : wilder (dans le groupe des admins locaux)
Mot de passe : Azerty1*
Adresse IP fixe : 172.16.10.20/24

- ##### Difficultés rencontrées : problèmes techniques rencontrés
- Problème lors de la connexion de tightVNCviewer au serveur à distance:
Message d'erreur au niveau du mot de passe



- ##### Solutions trouvées : Solutions et alternatives trouvées
 Dans le panneau de configuration de TightVNCserver: reconfiguration du mot de passe pour l'accès à distance



- ##### Améliorations possibles : suggestions d’améliorations futures

