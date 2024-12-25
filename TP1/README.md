# Spatial Database - TD 1

## Objective
This tutorial guides you through the installation of PostgreSQL, the PostGIS extension, and the creation of a spatial database using PgAdmin 4.

---

## Requirements
- PostgreSQL (latest version)
- PostGIS (spatial database extension)
- PgAdmin 4

---

## Steps

### 1. Install PostgreSQL
1. Download PostgreSQL from [PostgreSQL Downloads](https://www.postgresql.org/download/).
2. Follow the installation guide for your operating system (Linux, macOS, or Windows).
3. During the installation, set a password for the default user (postgres).

---

### 2. Install PostGIS
1. During PostgreSQL installation, select all components, including the *Stack Builder*.
2. Launch the *Stack Builder* and select the PostgreSQL version installed.
3. Select *PostGIS* and other required tools to download.
4. Complete the installation process.

---

### 3. Create a Spatial Database using PgAdmin 4
1. Launch PgAdmin and log in using the password set for postgres.
2. Navigate to *Servers > PostgreSQL > Create > Database*.
3. Name your database (e.g., spatial-db-1) and save it.
4. Open the Query Tool for the new database and run the following SQL:
   ```sql
   CREATE EXTENSION postgis;
