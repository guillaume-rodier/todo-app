# Todo App (Django)

Guide rapide pour lancer le projet Django en local.

## Prérequis

- Python 3.12+ (ou version compatible avec Django 6)
- `pip`
- (Optionnel) `venv` pour isoler l'environnement

## Installation

Depuis la racine du projet :

```bash
python -m venv .venv
```

### Activer l'environnement virtuel

**Windows (PowerShell)**

```powershell
.venv\Scripts\Activate.ps1
```

**macOS / Linux**

```bash
source .venv/bin/activate
```

Puis installer les dépendances :

```bash
pip install -r requirements.txt
```

## Configuration `.env`

Créer le fichier local à partir de l'exemple :

```bash
cp .env.example .env
```

Sous Windows PowerShell :

```powershell
Copy-Item .env.example .env
```

Variables principales :

- `SECRET_KEY` : clé secrète Django
- `DEBUG` : `True` en local
- `DB_NAME`, `DB_USER`, `DB_PASSWORD`, `DB_HOST`, `DB_PORT` : configuration MySQL

## Initialiser la base de données

```bash
python manage.py migrate
```

## (Optionnel) Créer un superutilisateur

```bash
python manage.py createsuperuser
```

## Lancer le serveur en local

```bash
python manage.py runserver
```

Application disponible sur : [http://127.0.0.1:8000](http://127.0.0.1:8000)

## Commandes utiles

Créer des migrations après modifications des modèles :

```bash
python manage.py makemigrations
python manage.py migrate
```

Accéder à l'administration Django :

- URL : [http://127.0.0.1:8000/admin](http://127.0.0.1:8000/admin)
- Utiliser le compte créé via `createsuperuser`