# Générateur d’Arborescence de Projet avec Fonctions PHP

Ce script Python permet de générer une représentation visuelle d’un projet sous forme d’arborescence, en listant tous les fichiers et dossiers (sauf certains exclus), et en identifiant les fonctions définies dans les fichiers PHP. Le résultat est sauvegardé dans un fichier texte pour une consultation facile.

## 🧰 Fonctionnalités

- [x] Parcours récursif d’un dossier donné (par défaut, le dossier courant)  
- [x] Affichage structuré de l’arborescence du projet (`├──`, `└──`, etc.)  
- [x] Extraction des fonctions définies dans les fichiers `.php`  
- [x] Ignoration automatique de certains dossiers comme `node_modules` et `.git`  
- [x] Sauvegarde du résultat dans un fichier `arborescence_projet.txt`  

## 📂 Exemple de sortie

```text
├── index.php
    ↳ function connectDB()
    ↳ function loadUser()
├── includes
│   └── utils.php
│       ↳ function sanitizeInput()
└── assets
    └── style.css
```

## ⚙️ Utilisation

### Prérequis

- [ ] Python 3.x installé

### Lancer le script

```bash
python script.py
```

Le fichier `arborescence_projet.txt` sera généré à la racine du projet.

## 🧠 Détail technique

### Extraction des fonctions PHP

Le script utilise une expression régulière pour détecter les fonctions dans les fichiers `.php` :

```python
r'(?:public|protected|private)?\s*function\s+([a-zA-Z0-9_]+)\s*\('
```

Cela permet de repérer aussi bien les fonctions publiques, privées ou protégées.

### Arborescence

Le rendu visuel est généré avec des connecteurs ASCII (`├──`, `└──`, `│`, etc.), pour une lecture claire même dans un terminal ou un éditeur de texte.

### Dossiers exclus

- `node_modules`
- `.git`

Tu peux modifier la variable `EXCLUDED_DIRS` dans le script si tu veux adapter cette liste.

## ✍️ Auteur

Script écrit par **Laurent TOUCHET**