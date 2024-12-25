# Spatial_DB

This repository contains tutorials and resources for working with spatial databases using PostgreSQL, PostGIS, and QGIS. It is organized into three sections, each focusing on specific tasks related to spatial data management and analysis.

## Table of Contents

1. [Overview](#overview)
2. [Contents](#contents)
    - [TD1: Spatial Database Setup](#td1-spatial-database-setup)
    - [TD2: Creating Tables with Spatial Columns](#td2-creating-tables-with-spatial-columns)
    - [TD3: Spatial Analysis with PostGIS and QGIS](#td3-spatial-analysis-with-postgis-and-qgis)
3. [Requirements](#requirements)
4. [References](#references)

---

## Overview

This repository provides practical guides to:

- Set up PostgreSQL and PostGIS for spatial database operations.
- Create and manage spatial tables with different geometry types.
- Perform advanced spatial analyses using SQL and QGIS.

The tutorials are designed for users working with real-world spatial data and aim to integrate database management, GIS tools, and spatial analytics.

---

## Contents

### TD1: Spatial Database Setup

The first tutorial walks you through setting up a spatial database. It covers:

1. **Installing PostgreSQL and PostGIS**: A step-by-step guide to install and configure the necessary tools.
2. **Creating a Spatial Database**: Instructions to initialize a spatial database and verify the PostGIS setup.
3. **Setting up PgAdmin**: Details on how to manage your spatial database using the PgAdmin interface.

### TD2: Creating Tables with Spatial Columns

The second tutorial focuses on creating and managing spatial tables. Topics include:

1. **Creating Spatial Tables**: Examples of tables with Point, Polygon, and LineString geometries.
2. **Inserting Spatial Data**: How to use QGIS to add spatial data to the tables.
3. **Verifying Data**: Using SQL queries to verify and analyze the spatial data in your database.

### TD3: Spatial Analysis with PostGIS and QGIS

The third tutorial explores spatial data analysis, focusing on fire risk zones in Florida. Key tasks include:

1. **Importing Shapefiles**: Instructions to load shapefiles into your spatial database.
2. **Defining Fire Risk Zones**: Identifying and visualizing risk zones around specific parcels using PostGIS and QGIS.
3. **Advanced Spatial Queries**: Performing complex spatial operations, such as calculating distances, areas, and counts.

---

## Requirements

- **PostgreSQL**: Ensure it is installed and configured with the PostGIS extension.
- **PgAdmin**: For managing the database and running SQL queries.
- **QGIS**: For spatial data visualization and editing.
- **Data**: Include relevant shapefiles or datasets for spatial analysis.

---

## References

- [PostgreSQL Documentation](https://www.postgresql.org/)
- [PostGIS Documentation](https://postgis.net/)
- [QGIS Documentation](https://www.qgis.org/en/docs/)
- Florida Parcel Data: Link included in the TD3 section.

---

Feel free to contribute by adding new tutorials, fixing issues, or sharing ideas to enhance this repository.
