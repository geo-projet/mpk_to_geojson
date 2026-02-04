# MPK to GeoJSON Converter

Ce projet permet de convertir des fichiers **ArcGIS Map Package (.mpk)** en fichiers **GeoJSON**.

Le script extrait le contenu des fichiers `.mpk` (qui sont des archives ZIP ou 7z), localise les fichiers Shapefile (`.shp`) à l'intérieur, et les convertit en format GeoJSON. Il assure également que la projection des fichiers de sortie soit en **EPSG:4326 (WGS84)**.

## Prérequis

- Python 3.x
- Les bibliothèques listées dans `requirements.txt`

## Installation

1. Clonez ce dépôt ou téléchargez les fichiers.
2. Installez les dépendances :

```bash
pip install -r requirements.txt
```

*Note : L'installation de `geopandas` peut parfois nécessiter des dépendances systèmes supplémentaires (comme GDAL) sous Windows. L'utilisation de `conda` ou d'un environnement pré-configuré peut aider si pip échoue.*

## Utilisation

1. Placez vos fichiers `.mpk` dans le dossier `mpk_dir`.
2. Lancez le script :

```bash
python import_mpk.py
```

3. Les résultats seront générés dans le dossier `geojson_dir`. Chaque fichier `.mpk` aura son propre sous-dossier contenant les fichiers GeoJSON convertis.

## Fonctionnalités

- **Extraction automatique** : Gère les formats `.zip` et `.7z` (souvent utilisés pour les fichiers .mpk récents).
- **Reprojection** : Convertit automatiquement les coordonnées en Latitude/Longitude (WGS84) si nécessaire.
- **Organisation** : Trie les sorties dans des dossiers nommés selon le fichier source.

## Structure du projet

```
.
├── import_mpk.py       # Script principal
├── mpk_dir/            # Dossier d'entrée (à créer ou généré auto)
├── geojson_dir/        # Dossier de sortie (généré auto)
├── requirements.txt    # Dépendances
└── README.md           # Documentation
```
