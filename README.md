# Leafmap - Visualisation du changement d'occupation des sols

Leafmap est une bibliothèque Python puissante pour la création de cartes interactives et la visualisation de données géospatiales. Ce README se concentre sur l'utilisation de leafmap pour visualiser les changements d'occupation des sols dans plusieurs régions métropolitaines américaines, en utilisant les données de la National Land Cover Database (NLCD) de l'US Geological Survey (USGS).

## Installation

```bash
pip install leafmap
```

## Fonctionnalités principales

### 1. Importation de leafmap

```python
import leafmap.leafmap as leafmap
```

### 2. Affichage des fonds de carte disponibles

Leafmap offre une grande variété de fonds de carte :

```python
print(leafmap.basemaps.keys())
```

### 3. Création de cartes liées

Leafmap permet de créer des cartes côte à côte pour une comparaison facile :

```python
layers = ['Google Hybrid', 'Google Maps']
leafmap.linked_maps(rows=1, cols=2, height='400px', layers=layers)
```

### 4. Visualisation des changements d'occupation des sols

Utilisation des données NLCD pour visualiser les changements d'occupation des sols sur plusieurs années :

```python
layers = [f"NLCD {year} CONUS Land Cover" for year in [2001, 2006, 2011, 2016]]
labels = [f"NLCD {year}" for year in [2001, 2006, 2011, 2016]]

leafmap.linked_maps(
    rows=2,
    cols=2,
    height='500px',
    layers=layers,
    labels=labels,
    center=[latitude, longitude],
    zoom=zoom_level,
)
```

## Exemples d'utilisation

Le notebook fourni illustre la visualisation des changements d'occupation des sols pour six régions métropolitaines américaines :

1. Phoenix, Arizona
2. Houston, Texas
3. Austin, Texas
4. Dallas-Fort Worth, Texas
5. Seattle, Washington
6. Charlotte, Caroline du Nord

Chaque exemple utilise les données NLCD pour les années 2001, 2006, 2011 et 2016, permettant une comparaison visuelle de l'évolution de l'urbanisation sur cette période.

## Source des données

Les données utilisées proviennent de la National Land Cover Database (NLCD), développée par l'US Geological Survey (USGS) en partenariat avec plusieurs agences fédérales.

Source : https://www.mrlc.gov/data/nlcd-land-cover-conus-all-years

## Personnalisation

Le code peut être facilement adapté pour visualiser d'autres régions ou périodes en modifiant les coordonnées du centre, le niveau de zoom et les années des données NLCD.

## Contribution

Les contributions à leafmap sont les bienvenues. Veuillez consulter le guide de contribution sur le dépôt GitHub du projet pour plus d'informations.

## Licence

Leafmap est distribué sous licence MIT.

## Contact

Pour plus d'informations, visitez la [documentation officielle de leafmap](https://leafmap.org/).
