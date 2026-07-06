# DAY1_5

Projet Python réalisé avec **uv**, **Git** et **GitHub**.

---

# Table des matières

* [Présentation](#présentation)
* [Prérequis](#prérequis)
* [Installation](#installation)
* [Créer un projet depuis zéro](#créer-un-projet-depuis-zéro)
* [Structure du projet](#structure-du-projet)
* [Gestion des dépendances avec uv](#gestion-des-dépendances-avec-uv)
* [Utilisation](#utilisation)
* [Gestion de Git](#gestion-de-git)
* [Publier le projet sur GitHub](#publier-le-projet-sur-github)
* [Bonnes pratiques](#bonnes-pratiques)
* [Auteur](#auteur)

---

# Présentation

Ce projet constitue une base de développement Python utilisant :

* **Python**
* **uv** pour la gestion des environnements virtuels et des dépendances
* **Git** pour le versionnement
* **GitHub** pour le partage du code

L'objectif est d'obtenir une structure de projet reproductible et facilement maintenable.

---

# Prérequis

Les logiciels suivants doivent être installés.

* Python ≥ 3.13
* Git
* GitHub CLI (`gh`)
* uv

Vérifier les versions installées :

```bash
python --version
git --version
gh --version
uv --version
```

---

# Installation

## Cloner le dépôt

```bash
git clone https://github.com/Megane-b/DAY1_5.git
```

Entrer dans le dossier :

```bash
cd DAY1_5
```

Créer automatiquement l'environnement virtuel et installer toutes les dépendances :

```bash
uv sync
```

L'environnement virtuel `.venv` est créé automatiquement.

---

# Créer un projet depuis zéro

## 1. Se placer dans le dossier de travail

```bash
cd ~/Documents/DESU
```

---

## 2. Initialiser un nouveau projet

```bash
uv init DAY1_5
```

Entrer dans le projet :

```bash
cd DAY1_5
```

---

## 3. Organiser le projet

Créer quelques dossiers utiles :

```bash
mkdir src data scripts out
```

Créer un fichier `.gitignore` :

```bash
touch .gitignore
```

Exemple de contenu :

```gitignore
.venv/
__pycache__/
*.pyc
.ipynb_checkpoints/
.DS_Store
```

---

## 4. Créer l'environnement virtuel

```bash
uv sync
```

---

## 5. Installer les bibliothèques

Exemple :

```bash
uv add numpy
uv add pandas
uv add matplotlib
uv add seaborn
uv add scikit-learn
```

ou directement

```bash
uv add numpy pandas matplotlib seaborn scikit-learn
```

Les dépendances sont automatiquement ajoutées dans :

* `pyproject.toml`
* `uv.lock`

---

## 6. Initialiser Git

```bash
git init
```

Ajouter les fichiers :

```bash
git add .
```

Créer le premier commit :

```bash
git commit -m "Initial commit"
```

---

## 7. Publier sur GitHub

Créer le dépôt GitHub :

```bash
gh repo create DAY1_5 --public --source=. --remote=origin --push
```

Cette commande :

* crée le dépôt GitHub ;
* configure automatiquement le dépôt distant `origin` ;
* envoie le premier commit.

---

# Structure du projet

```
DAY1_5/
│
├── .venv/                # Environnement virtuel
├── data/                 # Données
├── out/                  # Résultats
├── scripts/              # Scripts
├── src/                  # Code source
│
├── .gitignore
├── .python-version
├── main.py
├── pyproject.toml
├── README.md
├── uv.lock
└── .git/
```

---

# Gestion des dépendances avec uv

## Installer une bibliothèque

```bash
uv add numpy
```

---

## Installer plusieurs bibliothèques

```bash
uv add numpy pandas matplotlib seaborn scikit-learn
```

---

## Synchroniser l'environnement

```bash
uv sync
```

---

## Mettre à jour les dépendances

```bash
uv lock --upgrade
uv sync
```

---

## Supprimer une bibliothèque

```bash
uv remove numpy
```

---

## Exécuter un script

```bash
uv run python main.py
```

ou

```bash
python main.py
```

si l'environnement est déjà activé.

---

# Utilisation

Lancer le programme principal :

```bash
uv run python main.py
```

Créer un nouveau script :

```bash
touch scripts/mon_script.py
```

Exécuter un script :

```bash
uv run python scripts/mon_script.py
```

---

# Gestion de Git

Vérifier l'état du dépôt :

```bash
git status
```

Ajouter les modifications :

```bash
git add .
```

Créer un commit :

```bash
git commit -m "Description des modifications"
```

Envoyer les modifications :

```bash
git push
```

Télécharger les modifications :

```bash
git pull
```

Voir l'historique :

```bash
git log
```

Historique compact :

```bash
git log --oneline
```

---

# Publier le projet sur GitHub

Créer le dépôt GitHub :

```bash
gh repo create DAY1_5 --public --source=. --remote=origin --push
```

Si le dépôt existe déjà :

```bash
git push origin master
```

ou

```bash
git push origin main
```

selon le nom de votre branche.

---

# Bonnes pratiques

* utiliser `uv add` plutôt que modifier `pyproject.toml` manuellement ;
* conserver les données dans `data/` ;
* placer les scripts dans `scripts/` ;
* développer le code réutilisable dans `src/` ;
* enregistrer les résultats dans `out/` ;
* effectuer un commit après chaque étape importante ;
* utiliser des messages de commit explicites ;
* ne jamais versionner le dossier `.venv/`.

---

# Workflow recommandé

```text
Créer le projet
        │
        ▼
uv init
        │
        ▼
Créer les dossiers
        │
        ▼
uv sync
        │
        ▼
uv add ...
        │
        ▼
git init
        │
        ▼
git add .
        │
        ▼
git commit
        │
        ▼
gh repo create
        │
        ▼
git push
```

---

# Auteur

**Mégane Barbosa-Grange**

DESU Data Science — 2026

---
