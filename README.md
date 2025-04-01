```markdown
# Application de Vote Django

Django Vote App est une application de vote complète. Vous devez vous inscrire pour afficher les votes et voter. Si vous avez déjà voté, vous ne pouvez pas voter à nouveau. Seul le propriétaire d'un vote peut ajouter, modifier, mettre à jour, supprimer un vote, ajouter des options, mettre à jour ou supprimer des choix, et clôturer un vote. Un vote clôturé ne peut plus être modifié et affiche uniquement les résultats finaux. L'application inclut une fonction de recherche et des filtres par nom, date de publication et nombre de votes. La pagination fonctionne même après application des filtres.

## Pour commencer

Ces instructions vous permettront de copier et exécuter le projet localement à des fins de développement et de test.

### Prérequis

- `Python == 3.5 ou supérieur`
- `Django == 2.0 ou supérieur`

### Installation

1. Ouvrez un terminal et exécutez :
```bash
git clone https://github.com/devmahmud/Django-vote-app.git
```

2. Ou téléchargez directement via :
```bash
https://github.com/devmahmud/Django-vote-app.git
```

### Migration de la base de données

Exécutez dans le terminal :
```bash
python manage.py makemigrations
python manage.py migrate
```

### Création d'un superutilisateur

Pour accéder à l'interface d'administration :
```bash
python manage.py createsuperuser
```

### Génération de données de test

1. Installez Faker :
```bash
pip install faker
```

2. Exécutez dans le shell Django :
```python
import seeder
seeder.seed_all(30)  # 30 = nombre d'entrées (ajustable)
```

## Configuration Email

Configurez les paramètres SMTP dans `settings.py` :
```python
EMAIL_HOST = '<hôte_smtp>'
EMAIL_PORT = '<port_smtp>'
EMAIL_HOST_USER = '<utilisateur_smtp>'
EMAIL_HOST_PASSWORD = '<mot_de_passe_smtp>'
DEFAULT_FROM_EMAIL = '<email_expéditeur>'
```

## Configuration OpenAI

1. **Créez un compte OpenAI** :  
   [https://platform.openai.com/signup](https://platform.openai.com/signup)

2. **Générez une clé API** :  
   [https://platform.openai.com/account/api-keys](https://platform.openai.com/account/api-keys)

3. **Ajoutez la clé à vos variables d'environnement** :
```bash
OPENAI_API_KEY=votre_clé_ici
```

## Authentification OAuth

<details>
<summary>Configuration Google</summary>

1. **Console Google Cloud** :  
   [https://console.cloud.google.com/](https://console.cloud.google.com/)

2. Créez un projet > Activez **Google Identity Platform**

3. Configurez l'écran de consentement OAuth

4. Créez des identifiants :
```python
SOCIAL_AUTH_GOOGLE_OAUTH2_KEY = 'votre-client-id'
SOCIAL_AUTH_GOOGLE_OAUTH2_SECRET = 'votre-client-secret'
```
</details>

<details>
<summary>Configuration Facebook</summary>

1. **Portail développeurs Facebook** :  
   [https://developers.facebook.com/](https://developers.facebook.com/)

2. Créez une application > Configurez les URI de redirection

3. Récupérez les identifiants :
```python
SOCIAL_AUTH_FACEBOOK_OAUTH2_KEY = 'votre-client-id'
SOCIAL_AUTH_FACEBOOK_OAUTH2_SECRET = 'votre-client-secret'
```
</details>

<details>
<summary>Configuration LinkedIn</summary>

1. **Portail développeurs LinkedIn** :  
   [https://www.linkedin.com/developers/](https://www.linkedin.com/developers/)

2. Créez une application > Configurez les URLs de callback

3. Récupérez les identifiants :
```python
SOCIAL_AUTH_LINKEDIN_OAUTH2_KEY = 'votre-client-id'
SOCIAL_AUTH_LINKEDIN_OAUTH2_SECRET = 'votre-client-secret'
```
</details>

## Lancement du serveur

```bash
python manage.py runserver
```

Accédez à [http://127.0.0.1:8000](http://127.0.0.1:8000) dans votre navigateur.

## Captures d'écran

| Page d'accueil | Connexion | Inscription |
|----------------|-----------|-------------|
| ![Home](https://user-images.githubusercontent.com/19981097/51409444-0e40a600-1b8c-11e9-9ab0-27d759db8973.jpg) | ![Login](https://user-images.githubusercontent.com/19981097/51409509-36c8a000-1b8c-11e9-845a-65b49262aa53.png) | ![Register](https://user-images.githubusercontent.com/19981097/51409562-5cee4000-1b8c-11e9-82f6-1aa2df159528.png) |

| Liste des votes | Création | Résultats |
|-----------------|----------|-----------|
| ![Votes](https://user-images.githubusercontent.com/19981097/51409728-d423d400-1b8c-11e9-8903-4c08ba64512e.png) | ![Add](https://user-images.githubusercontent.com/19981097/51409796-fe759180-1b8c-11e9-941b-c1202956cca4.png) | ![Results](https://user-images.githubusercontent.com/19981097/51409932-60ce9200-1b8d-11e9-9c83-c59ba498ca8b.png) |

## Auteur

**Mahmudul Alam**  
**Mahmudul Alam**  
**Mahmudul Alam**  

<div align="center">
  <h3>🙏 Merci ! 🙏</h3>
</div>
```# voting
