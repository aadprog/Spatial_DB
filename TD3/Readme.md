# Spatial Database - TD-3

## Overview

This tutorial guides you through using **PostGIS** and **QGIS** to analyze spatial data, focusing on fire risk zones around specific parcels in Florida. The tasks include importing shapefiles, performing spatial queries, and visualizing the data.

---

## Requirements

- **PostGIS** installed and enabled in PostgreSQL.
- **QGIS** for spatial visualization and filtering.
- Florida parcel shapefile (download [here](https://maps.leegov.com/datasets/80708a2f5f56426f94c8be97c182176b/about)).
- Access to **pgAdmin** for executing SQL queries.

---

## Instructions

### 1. Import Shapefile into PostGIS

1. **Download the shapefile** from the link provided.
2. **Open PostGIS Shapefile Import/Export Manager**:
   - On Windows, search for "Shapefile Import/Export Manager" using the Windows search bar.
3. Import the shapefile into a PostgreSQL table named `parcels`.

---

### 2. Initial Queries

1. Count total parcels:
   ```sql
   SELECT COUNT(*) FROM parcels;
   ```
2. Preview the table:
   ```sql
   SELECT * FROM parcels LIMIT 5;
   ```
### 3. Identify Fire Point
Determine the centroid of the target parcel (gid = 462273) as the fire point:

```sql
SELECT ST_Centroid(geom) AS fire_point
FROM parcels
WHERE gid = 462273;
```
### 4. Define Fire Risk Zone

#### In QGIS:

1. **Duplicate the parcels layer** and rename it to `fire-risk`.

2. **Apply a filter** to the new layer:
   - Right-click the layer and select **Filter**.
   - Use the following filtering expression:

     ```sql
     ST_DWithin(geom, (SELECT ST_Centroid(geom) FROM "public"."parcels" WHERE gid = 462273), 1000)
     ```

3. **Adjust symbology** to visualize the fire risk zones.

4. **For an additional fire point (gid = 460957)**, update the filter to:

     ```sql
     ST_DWithin(geom, (SELECT ST_Centroid(geom) FROM "public"."parcels" WHERE gid IN (462273, 460957)), 1000)
     ```
### 5. Advanced Queries in pgAdmin

#### 1. Count parcels within 1 km of the two fire points:

```sql
SELECT COUNT(*)
FROM parcels
WHERE ST_DWithin(
    geom,
    (SELECT ST_Union(ST_Centroid(geom)) 
     FROM parcels 
     WHERE gid IN (462273, 460957)), 
    1000
);
```
#### 2. Calculate the total area of parcels near the fire points:

```sql
SELECT SUM(ST_Area(geom))
FROM parcels
WHERE ST_DWithin(
    geom,
    (SELECT ST_Union(ST_Centroid(geom)) 
     FROM parcels 
     WHERE gid IN (462273, 460957)), 
    1000
);
```

## References

- [PostGIS Documentation](https://postgis.net/documentation/)
- [Florida Parcel Data](https://www.floridaparceldata.com/)
- [Arduino](https://www.arduino.cc/)



