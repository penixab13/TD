# Spatial Database - TD 3

This README provides instructions for completing the exercises in *TD-3: Spatial SQL Functions, as part of the course on **Spatial Databases*.

## Table of Contents
1. [Overview](#overview)
2. [Tasks](#tasks)
   - [Task 1: Import Shapefile into PostGIS](#task-1-import-shapefile-into-postgis)
   - [Task 2: Query Parcels](#task-2-query-parcels)
   - [Task 3: Determine Fire Point (Centroid)](#task-3-determine-fire-point-centroid)
   - [Task 4: Identify Risk Zone](#task-4-identify-risk-zone)
   - [Task 5: Advanced Queries](#task-5-advanced-queries)
3. [Tools and Requirements](#tools-and-requirements)

## Overview
This exercise involves using PostGIS to analyze spatial data related to parcels in Florida. You will determine the parcels located within a 1 km radius of a fire point and calculate relevant spatial metrics.

## Tasks

### Task 1: Import Shapefile into PostGIS
1. Download the shapefile of Florida parcels from [this link](https://maps.leegov.com/datasets/80708a2f5f56426f94c8be97c182176b/about).
2. Use the *PostGIS Shapefile Import/Export Manager* to import the shapefile:
   - Open the Import/Export Manager (search "Shapefile Import" on Windows).
   - Select the shapefile and import it into a PostgreSQL table.

### Task 2: Query Parcels
1. In *pgAdmin*, run the following queries:
    sql
    SELECT COUNT(*) FROM parcels;
    
    sql
    SELECT * FROM parcels LIMIT 5;
    

### Task 3: Determine Fire Point (Centroid)
1. Identify the centroid of a specific parcel (e.g., gid = 462273):
    sql
    SELECT ST_Centroid(geom) AS fire_point
    FROM parcels
    WHERE gid = 462273;
    

### Task 4: Identify Risk Zone
1. Use *QGIS* to duplicate the parcels layer and name it fire-risk.
2. Apply a filter to identify parcels within 1 km of the fire point:
    - Filter expression:
      sql
      ST_DWithin(geom, (SELECT ST_Centroid(geom) FROM "public"."parcels" WHERE gid = 462273), 1000)
      
3. Change the symbology of the layer to visualize the risk zones.
4. Add a second fire point (gid = 460957) and update the filter to include both parcels.

### Task 5: Advanced Queries
1. Use *pgAdmin* (or QGIS query editor) to answer the following:
   - How many parcels are within 1 km of the two fire points (gid = 460957 and 462273)?
   - What is the total area of parcels close to the fire points?

## Tools and Requirements
- *PgAdmin*: For executing SQL queries.
- *PostGIS*: PostgreSQL extension for spatial operations.
- *QGIS*: For visualizing and editing spatial data.
- *Shapefile*: Dataset of Florida parcels.

## Notes
- Refer to the [PostGIS Documentation](https://postgis.net/docs/reference.html) for details on spatial functions.
- Ensure PostGIS is properly configured in your PostgreSQL setup.

---

For questions or clarifications, contact your instructor or refer to course materials.
