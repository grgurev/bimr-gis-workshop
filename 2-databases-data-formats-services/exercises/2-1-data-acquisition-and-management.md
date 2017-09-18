## Data processing and handling techniques for the purposes of efficient biodiversity data management and reporting
### Exercise 3 - Data acquisition and management
#### Objective - Getting familiar with data acquisition and storing it in the project database
Document version: 2017-09-14
Document author: Petra Štrbenac; Marin Grgurev, PhD

---

**Task 1: Create SpatialLite database using QGIS.**
Now that you have taken necessary steps to prepare your data, you will create new empty SpatialLite database in which you're going to import your data by using browser panel.

**Steps to do:**
1. Right click on the SpatialLite entry in the browser tree and create new database.
2. Specify where on the file system you want to store the file and name it qgis-sl.db.
3. Right click on the SpatialLite entry and select New Connection item

---

**Task 2: Create new database layer.**
After configuring your new database and creating the connection you will find that the entry in Browser tree has nothing underneath it and the only thing you can do at this point is to delete the connection. This is of course because we haven't added any tables to this database.
Find the button to create a new layer and use the dropdown menu to create a new SpatialLite layer or select Layer -> New -> New SpatialLite Layer.

**Steps to do:**
1. Select the database we created in the previous steps in the drop down.
2. Give the layer the name places.
3. Tick the checkbox next to Create an auto-incrementing primary key.
4. Add several attributes to the table.
5. Click the refresh button at the top of the Browser and you should now see your places table listed.

You can right click on the table and view its properties as we did in the previous exercise. From here you can start an editing session and start adding data to your new database directly.

---

**Task 3: Import external data to database.**
To import external Shapefile to your SpatiaLite database we will use DB Manager. To work with Spatial Databases in QGIS you will use export and import data commands to/from database.

1. Click the Import layer/file button on the toolbar in the DB Manager dialog.
2. Select the shapefile located in \data\BiogeoRegions2016.shp as the input dataset.
3. Click the Update Options button to pre-fill some of the form values.
4. Make sure that the Create new table option is selected
5. Enable the checkbox to Create Spatial Index
6. Click OK to perform the import.
7. Dismiss the dialog letting you know that the import was successful
8. Click the Refresh button on the DB Manager Toolbar.

You can now inspect the table in your database by clicking on it in the Tree.
Right clicking on the table in the Tree and a selecting Add to Canvas will add the table as a layer in your map.
