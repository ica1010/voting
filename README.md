Voici une version mise à jour de la documentation incluant une section "Cas d'utilisation" qui détaille plusieurs scénarios typiques d'utilisation de l'application :

---

# Documentation de l'Application de Vote Django

Chaque groupe doit fournir une documentation détaillée présentant les fonctionnalités déjà développées, accompagnée de captures d'écran illustratives. Cette documentation a pour but de guider l'utilisateur à travers l'installation, la configuration et l'utilisation de l'application de vote.

## 1. Présentation Générale

**Django Vote App** est une application de vote en ligne qui permet aux utilisateurs de s'inscrire, de consulter et de participer aux votes. Le système est conçu pour garantir une utilisation sécurisée et transparente, en limitant les actions de vote à une seule participation par utilisateur et en réservant les actions de modification aux propriétaires des votes.

## 2. Fonctionnalités Développées

- **Inscription et Authentification :**  
  - Inscription obligatoire pour accéder à l'interface de vote.
  - Authentification sécurisée avec gestion des sessions.
  - Intégration d'OAuth pour Google, Facebook et LinkedIn afin de faciliter l'inscription et la connexion.

- **Gestion des Votes :**  
  - Création d'un nouveau vote par l'utilisateur propriétaire.
  - Possibilité d'ajouter, de modifier ou de supprimer un vote (action réservée au propriétaire).
  - Chaque utilisateur ne peut voter qu'une seule fois par sondage.
  - Clôture des votes : une fois un vote clôturé, aucune modification n'est possible et seuls les résultats finaux sont affichés.

- **Options et Choix :**  
  - Ajout d'options et de choix pour chaque vote.
  - Mise à jour ou suppression des options et des choix par le propriétaire.

- **Recherche et Filtrage :**  
  - Fonction de recherche intégrée pour retrouver rapidement un vote.
  - Filtres disponibles par nom, date de publication et nombre de votes.
  - La pagination reste fonctionnelle même après l'application des filtres.

- **Génération de Données de Test :**  
  - Utilisation de Faker pour la création de jeux de données factices à des fins de test (exemple : 30 entrées).

- **Notifications par Email :**  
  - Configuration SMTP pour l'envoi d'emails (notifications, validations, etc.).

- **Intégration OpenAI :**  
  - Utilisation d'API d'OpenAI pour des fonctionnalités avancées (si besoin).

## 3. Cas d'Utilisation

Voici quelques cas d'utilisation illustrant comment différents utilisateurs interagissent avec l'application :

### 3.1. Inscription et Authentification

- **En tant que nouvel utilisateur, je souhaite m'inscrire :**  
  1. Accéder à la page d'inscription.
  2. Remplir le formulaire avec mes informations personnelles (nom, email, mot de passe, etc.).
  3. Valider l'inscription pour créer mon compte.
  4. Recevoir une confirmation par email (si la configuration SMTP est activée).

- **En tant qu'utilisateur existant, je souhaite me connecter :**  
  1. Accéder à la page de connexion.
  2. Saisir mes identifiants (email et mot de passe ou via un fournisseur OAuth).
  3. Être redirigé vers la page d'accueil avec mes votes disponibles.

### 3.2. Gestion des Votes

- **En tant qu'utilisateur connecté, je souhaite créer un nouveau vote :**  
  1. Cliquer sur l'option "Créer un vote" dans l'interface.
  2. Remplir le formulaire de création en indiquant le titre, la description, et les options du vote.
  3. Soumettre le formulaire pour enregistrer le vote.
  4. Visualiser le vote nouvellement créé dans la liste des votes.

- **En tant que propriétaire d'un vote, je souhaite modifier ou supprimer mon vote :**  
  1. Accéder à la liste de mes votes.
  2. Sélectionner un vote existant.
  3. Utiliser les options "Modifier" ou "Supprimer" disponibles.
  4. Confirmer l'action pour mettre à jour ou supprimer le vote.

- **En tant qu'utilisateur, je souhaite participer à un vote :**  
  1. Consulter la liste des votes ouverts.
  2. Sélectionner un vote auquel je n'ai pas encore participé.
  3. Choisir mon option parmi les propositions disponibles.
  4. Valider mon vote.
  5. Ne pas être autorisé à voter à nouveau pour le même sondage.

- **En tant que propriétaire, je souhaite clôturer un vote :**  
  1. Accéder à mon vote depuis l'interface de gestion.
  2. Sélectionner l'option "Clôturer le vote".
  3. Confirmer la clôture qui empêchera toute modification ultérieure et affichera les résultats finaux.

### 3.3. Recherche et Filtrage

- **En tant qu'utilisateur, je souhaite rechercher un vote spécifique :**  
  1. Utiliser la barre de recherche en haut de l'interface.
  2. Entrer un mot-clé lié au nom ou à la description du vote.
  3. Visualiser les résultats filtrés.

- **En tant qu'utilisateur, je souhaite filtrer les votes par date ou nombre de votes :**  
  1. Utiliser les filtres disponibles sur la page de liste des votes.
  2. Sélectionner le critère souhaité (date de publication, nombre de votes, etc.).
  3. Voir la liste des votes mise à jour selon le filtre appliqué, avec pagination fonctionnelle.

## 4. Installation et Configuration

### Prérequis

- **Python :** Version 3.5 ou supérieure.
- **Django :** Version 2.0 ou supérieure.

### Clonage du Projet

Ouvrez un terminal et clonez le projet depuis GitHub :

```bash
git clone https://github.com/devmahmud/Django-vote-app.git
```

Ou téléchargez directement via :  
[https://github.com/devmahmud/Django-vote-app.git](https://github.com/devmahmud/Django-vote-app.git)

### Migration de la Base de Données

Dans votre terminal, exécutez :

```bash
python manage.py makemigrations
python manage.py migrate
```

### Création d'un Superutilisateur

Pour accéder à l'interface d'administration :

```bash
python manage.py createsuperuser
```

### Génération de Données de Test

1. Installez Faker :

```bash
pip install faker
```

2. Dans le shell Django, exécutez :

```python
import seeder
seeder.seed_all(30)  # 30 représente le nombre d'entrées (modifiable)
```

## 5. Configuration des Services Complémentaires

### Configuration Email

Dans le fichier `settings.py`, configurez les paramètres SMTP :

```python
EMAIL_HOST = '<hôte_smtp>'
EMAIL_PORT = '<port_smtp>'
EMAIL_HOST_USER = '<utilisateur_smtp>'
EMAIL_HOST_PASSWORD = '<mot_de_passe_smtp>'
DEFAULT_FROM_EMAIL = '<email_expéditeur>'
```

### Configuration OpenAI

1. **Créer un compte OpenAI :**  
   [https://platform.openai.com/signup](https://platform.openai.com/signup)

2. **Générer une clé API :**  
   [https://platform.openai.com/account/api-keys](https://platform.openai.com/account/api-keys)

3. **Ajouter la clé aux variables d'environnement :**

```bash
OPENAI_API_KEY=votre_clé_ici
```

### Authentification OAuth

#### Google

1. Accédez à la [Console Google Cloud](https://console.cloud.google.com/).
2. Créez un projet et activez **Google Identity Platform**.
3. Configurez l'écran de consentement OAuth.
4. Créez des identifiants :

```python
SOCIAL_AUTH_GOOGLE_OAUTH2_KEY = 'votre-client-id'
SOCIAL_AUTH_GOOGLE_OAUTH2_SECRET = 'votre-client-secret'
```

#### Facebook

1. Rendez-vous sur le [Portail développeurs Facebook](https://developers.facebook.com/).
2. Créez une application et configurez les URI de redirection.
3. Récupérez les identifiants :

```python
SOCIAL_AUTH_FACEBOOK_OAUTH2_KEY = 'votre-client-id'
SOCIAL_AUTH_FACEBOOK_OAUTH2_SECRET = 'votre-client-secret'
```

#### LinkedIn

1. Visitez le [Portail développeurs LinkedIn](https://www.linkedin.com/developers/).
2. Créez une application et configurez les URLs de callback.
3. Récupérez les identifiants :

```python
SOCIAL_AUTH_LINKEDIN_OAUTH2_KEY = 'votre-client-id'
SOCIAL_AUTH_LINKEDIN_OAUTH2_SECRET = 'votre-client-secret'
```

## 6. Lancement du Serveur

Pour démarrer le serveur de développement, exécutez :

```bash
python manage.py runserver
```

Accédez ensuite à l'application via votre navigateur à l'adresse :  
[http://127.0.0.1:8000](http://127.0.0.1:8000)

## 7. Captures d'Écran

### Page d'Accueil, Connexion et Inscription

| Page d'accueil | Connexion | Inscription |
|----------------|-----------|-------------|
| ![Home](https://user-images.githubusercontent.com/19981097/51409444-0e40a600-1b8c-11e9-9ab0-27d759db8973.jpg) | ![Login](https://user-images.githubusercontent.com/19981097/51409509-36c8a000-1b8c-11e9-845a-65b49262aa53.png) | ![Register](https://user-images.githubusercontent.com/19981097/51409562-5cee4000-1b8c-11e9-82f6-1aa2df159528.png) |

### Gestion des Votes

| Liste des votes | Création de vote | Résultats |
|-----------------|------------------|-----------|
| ![Votes](https://user-images.githubusercontent.com/19981097/51409728-d423d400-1b8c-11e9-8903-4c08ba64512e.png) | ![Add](https://user-images.githubusercontent.com/19981097/51409796-fe759180-1b8c-11e9-941b-c1202956cca4.png) | ![Results](https://user-images.githubusercontent.com/19981097/51409932-60ce9200-1b8d-11e9-9c83-c59ba498ca8b.png) |

## 8. menbres du groupe
APETOGBO
LABITEY Stéphane
AMETONOU Kossi Ghislin

## 9. Conclusion

Cette documentation offre une vue complète des fonctionnalités de l'application Django Vote App, depuis l'installation et la configuration jusqu'à la gestion avancée des votes, l'intégration de services tiers et les cas d'utilisation typiques. Elle permet aux utilisateurs et aux développeurs de comprendre et de déployer l'application rapidement, tout en s'appuyant sur des captures d'écran pour visualiser chaque étape du processus.

