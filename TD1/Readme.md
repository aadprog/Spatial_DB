# Spatial Database Setup with PostgreSQL and PostGIS

This guide provides step-by-step instructions to install PostgreSQL, set up PostGIS, and create a spatial database using PgAdmin 4.

## Requirements
- **Operating System**: Compatible with Linux, macOS, Windows, BSD, and Solaris.
- **Internet Connection**: Required for downloading additional tools and extensions.

---

## Steps to Install and Configure

### 1. Install PostgreSQL
1. Visit the [PostgreSQL Download Page](https://www.postgresql.org/download/).
2. Download the appropriate version for your operating system.
3. Follow the installation instructions for your system (Windows, Linux, macOS).
4. During installation:
   - Define a password for the `postgres` user (ensure it is memorable as it will be required later).

---

### 2. Install PostGIS
1. Ensure all components are selected during the PostgreSQL installation.
2. When prompted, enable **Stack Builder** to download PostGIS.
3. Follow the Stack Builder instructions:
   - Select the PostgreSQL version corresponding to your installation.
   - Choose **PostGIS** from the available applications.
4. Complete the installation process:
   - Specify the installation folder.
   - Close the setup once finished.

---

### 3. Create a Spatial Database in PgAdmin 4
1. Launch **PgAdmin 4**.
2. Log in using the password defined during PostgreSQL installation.
3. Expand the `Servers` tree, right-click on PostgreSQL, and select:
   - `Create > Database`.
4. Enter a name for your database (e.g., `spatial-db-1`) and save.
5. Add the PostGIS extension:
   - Navigate to your new database.
   - Open the **Query Tool** and run the following SQL command:
     ```sql
     CREATE EXTENSION postgis;
     ```
   - Execute the query (press **F5** or click the run button).

6. Verify the extension:
   - Expand your database schema.
   - Navigate to `Schemas > Public > Tables`.
   - Ensure a table named `spatial_ref_sys` is present.

---

## Notes
- Ensure your PostgreSQL version is compatible with the PostGIS extension.
- The `spatial_ref_sys` table confirms a successful PostGIS setup.

---

## References
- Official PostgreSQL Documentation: [https://www.postgresql.org/](https://www.postgresql.org/)
- PostGIS Documentation: [https://postgis.net/](https://postgis.net/)
