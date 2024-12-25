# Spatial Database - TD 2

This README provides instructions and information for completing the exercises in *TD-2: Creating Tables with Spatial Columns, as part of the course on **Spatial Databases*.

## Table of Contents
1. [Overview](#overview)
2. [Tasks](#tasks)
   - [Task 1: Creating Spatial Tables (Points)](#task-1-creating-spatial-tables-points)
   - [Task 2: Creating Spatial Tables (Polygons)](#task-2-creating-spatial-tables-polygons)
   - [Task 3: Creating Spatial Tables (Lines)](#task-3-creating-spatial-tables-lines)
3. [Tools and Requirements](#tools-and-requirements)

## Overview
This tutorial focuses on creating and managing spatial tables using PostgreSQL/PostGIS and integrating them with QGIS. The tasks involve creating tables with spatial columns, inserting spatial data, and querying them using PgAdmin.

## Tasks

### Task 1: Creating Spatial Tables (Points)
1. Use PgAdmin to create a table named points_of_interests with a geometry column of type Point:
    sql
    CREATE TABLE points_of_interests (
        id SERIAL PRIMARY KEY,
        name VARCHAR(255),
        geom GEOMETRY(Point, 4326)
    );
    
2. Insert data into this table using QGIS:
    - Right-click on PostgreSQL in the QGIS explorer panel and create a new connection.
    - Provide the necessary database connection details and test the connection.
    - Once connected, double-click the points_of_interests table to add it as a layer in QGIS.
    - Switch to editing mode, add points, and save your changes.

3. Verify the data in PgAdmin by running:
    sql
    SELECT * FROM points_of_interests;
    

### Task 2: Creating Spatial Tables (Polygons)
1. Use PgAdmin to create a table named zones_protegees with a geometry column of type Polygon:
    sql
    CREATE TABLE zones_protegees (
        id SERIAL PRIMARY KEY,
        name VARCHAR(255),
        geom GEOMETRY(Polygon, 4326)
    );
    
2. Insert data into this table using QGIS, following the same steps as in Task 1.
3. Verify the data in PgAdmin by running:
    sql
    SELECT * FROM zones_protegees;
    

### Task 3: Creating Spatial Tables (Lines)
1. Follow a similar approach to create a table with a geometry column of type LINESTRING. Adjust the table creation SQL command and QGIS workflow accordingly.

## Tools and Requirements
- *PgAdmin*: For managing PostgreSQL and PostGIS databases.
- *PostGIS*: PostgreSQL extension for spatial databases.
- *QGIS*: For spatial data visualization and editing.
- *SQL*: For querying and managing the spatial tables.

## Notes
- Ensure PostGIS is enabled in your PostgreSQL database.
- Always test connections between QGIS and the PostgreSQL database before proceeding with data editing.

---

For any questions or issues, please refer to your instructor or course materials.
