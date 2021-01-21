# Compte-rendu 21 janvier 2021

Acheté un serveur surpuissant, qui peut servir à héberger plusieurs applis dont Eclipse Che

**Proxmox** sert à gérer des VM, et **Kubernetes** serait dans des VM. A voir si on automatise tout le processus de déploiement.
On déploierait Kubernetes avec **OKD**, qui est l'équivalent de Fedora pour OpenShift. Utilisation d'Ansible ?

Une ou deux VM avec des OS classiques, et d'autres destinées à faire tourner des containers.

Déploiement sur Kubernetes de :

- **Eclipse Che**
- Postgres qui sert de stockage persistant
- Keycloak pour l'authentification
- frontend pour Che
- pour chaque utilisateur, son *namespace* :
  - espace de stockage
  - conteneurs dont l'utilisateur a besoin pour travailler
    - Theia, l'IDE (TypeScript, compat VS Code), le "Eclipse nouvelle génération"
    - selon le projet de dev, PHP + Composer, Java...
    
Adressage des IP des VM, va-t-on devoir voir avec la DISI ? Bonne question, Dzenan dit que chaque VM doit avoir une IP publique mais pas sûr avec OKD, on peut envisager un sous-domaine pour les applis comme la nôtre et VirtLabs

Deux grands aspects dans le projet pour deux sous-équipes :

- Kubernetes, gérer la charge de bcp de connexions d'étudiants : infra cloud
- Eclipse Che, comment le modifier pour l'usage pédagogique : dev cloud
  - intégration avec Moodle : workspaces selon les modules ou les séances de TP
  
Idéalement, projet prêt pour la rentrée 2021 pour pouvoir le tester avec les étudiants. A terme, ça peut devenir une solution durable. Ca correspondrait à certains besoins mais pas d'autres : au lieu d'installer les outils de dev, "on clique juste". Pour le savoir, il faut pouvoir le tester avec les étudiants

Pour la méthode de taff, on peut faire du "break it, fix it". C'est dur de se coordonner à 4 et tout le monde a envie de toucher à tout, à voir comment on gère ça

Créer le repo en open source peut être sympa

"Je vous laisse vous démerder"

Réunions 1er février 16h puis 15 février, on se verra avant pour voir les accès à la machine et les premières install lundi 25 à 16h

