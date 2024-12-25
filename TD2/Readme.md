# Création de Tables avec Colonnes Spatiales


Ce guide détaille les étapes nécessaires pour créer des tables spatiales dans une base de données PostgreSQL avec PostGIS, en utilisant PgAdmin et QGIS.

---

## 1. Création d'une Table Spatiale avec des Points

### 1.1 Créer la Table dans PgAdmin
Utilisez la commande SQL suivante pour créer une table nommée `points_of_interests` contenant une colonne géométrique de type `Point` :

```sql
CREATE TABLE points_of_interests (
    id SERIAL PRIMARY KEY,
    nom VARCHAR(255),
    geom GEOMETRY(Point, 4326)
);
```
### 1.2 Insérer des Données avec QGIS
Dans QGIS, procédez comme suit :
1. Accédez au panneau **Explorateur**.
2. Faites un clic droit sur **PostgreSQL**, puis sélectionnez **Nouvelle connexion**.
3. Entrez les informations de connexion requises et testez la connexion.
4. Double-cliquez sur la table `points_of_interests` pour l’ajouter comme une couche dans QGIS.
5. Passez en mode **Édition**, ajoutez des points, et sauvegardez.

### 1.3 Vérifier les Données dans PgAdmin
Exécutez la commande SQL suivante pour afficher les données insérées :
```sql
SELECT * FROM points_of_interests;
```
## 2. Création d'une Table Spatiale avec des Polygones

### 2.1 Créer la Table dans PgAdmin
Utilisez la commande SQL suivante pour créer une table nommée `zones_protegees` contenant une colonne géométrique de type `Polygon` :
```sql
CREATE TABLE zones_protegees (
    id SERIAL PRIMARY KEY,
    nom VARCHAR(255),
    geom GEOMETRY(Polygon, 4326)
);
```
### 2.2 Insérer des Données avec QGIS
Répétez les étapes mentionnées pour les points.  
Ajoutez cette fois des polygones en mode **Édition**, puis sauvegardez.

### 2.3 Vérifier les Données dans PgAdmin
Exécutez la commande SQL suivante pour afficher les données insérées :
```sql
SELECT * FROM zones_protegees;
```

## 3. Création d'une Table Spatiale avec des Lignes (LineString)
## 3.1 Créer la Table dans PgAdmin

Utilisez la commande SQL suivante pour créer une table avec une colonne géométrique de type `LineString` :

```sql
CREATE TABLE chemins (
    id SERIAL PRIMARY KEY,
    nom VARCHAR(255),
    geom GEOMETRY(LineString, 4326)
);
```
## 3.2 Insérer des Données avec QGIS

Ajoutez des lignes (`LineString`) en suivant les mêmes étapes que pour les points et les polygones.  
Passez en mode Édition, dessinez les lignes, et sauvegardez.

## 3.3 Vérifier les Données dans PgAdmin

Exécutez la commande SQL suivante pour afficher les données insérées :

```sql
SELECT * FROM chemins;
```

## Notes

- Toutes les géométries utilisent le système de coordonnées EPSG:4326.
- QGIS permet d'insérer et de modifier facilement des données spatiales directement dans les tables PostgreSQL.

## Références

- [Documentation PostgreSQL](https://www.postgresql.org/docs/)
- [Documentation PostGIS](https://postgis.net/documentation/)
- [Documentation QGIS](https://qgis.org/en/docs/)
