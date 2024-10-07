# Product Backlog

- **Installer et configurer un serveur Windows Server 2022**
- **Installer et configurer un client Windows 10 Pro**
- **Réaliser les livrables:**
  - **README.md**
    - Documentation générale:
      - Présentation du projet, objectifs finaux
      - Introduction : mise en contexte
      - Membres du groupe de projet (rôles par sprint)
      - Choix techniques : quel OS, quelle version, etc.
      - Difficultés rencontrées : problèmes techniques rencontrés
      - Solutions trouvées : solutions et alternatives trouvées
      - Améliorations possibles : suggestions d’améliorations futures

  - **INSTALL.md**
    - Documentation pour les administrateurs:
      - Prérequis techniques
      - Étapes d'installation et de configuration : instruction étape par étape
      - FAQ : solutions aux problèmes connus et courants liés à l’installation et à la configuration

  - **USER_GUIDE.md**
    - Documentation pour les utilisateurs:
      - Utilisation de base : comment utiliser - les fonctionnalités clés
      - Utilisation avancée : comment utiliser au mieux les options
      - FAQ : solutions aux problèmes connus et courants liés à l’utilisation

# Sprint Planning

- Installer et configurer un serveur Windows Server 2022 et un client Windows 10 Pro
        Pour un serveur Windows Server 2022 :
      Nom : SRVWIN01
      Compte : Administrator (dans le groupe des admins locaux)
      Mot de passe : Azerty1*
      Adresse IP fixe : 172.16.10.10/24

        Pour un client WindowWILDEs 10 : 
    Nom : CLIWIN01
    Compte utilisateur : wilder (dans le groupe des admins locaux)
    Mot de passe : Azerty1*
    Adresse IP fixe : 172.16.10.20/24

- Installer TightVNC sur le serveur et le client (deux versions différentes)

# Configuration du Bureau à Distance sur le Serveur

1. Allez dans **Propriétés du système** (cliquez avec le bouton droit de la souris sur « Ce PC » > Propriétés).
2. Cliquez sur **Paramètres du bureau à distance**.
3. Activez l'option **Autoriser les connexions à distance à cet ordinateur**.
4. Assurez-vous que l'option **Authentification de niveau réseau (NLA)** est sélectionnée pour plus de sécurité.
5. Cliquez sur **Appliquer** et **OK**.
