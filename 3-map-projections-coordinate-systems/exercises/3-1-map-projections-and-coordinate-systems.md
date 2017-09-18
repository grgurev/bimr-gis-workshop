## Data processing and handling techniques for the purposes of efficient biodiversity data management and reporting
### Exercise 3-1 - Geographical concepts
#### Objective - Explore and understand map projections and coordinate systems
Document version: 2017-09-18
Document author: Marin Grgurev, PhD

---

**Task 1 – Explore the coordinate reference system of visible layers and current project.**

Objective: Learn where to find information about defined coordinate reference
system for data layers and current project.

**Steps to do:**

1. Open QGIS.
2. On menu bar click on Project > Properties and select CRS tab.
3. Find out what is the coordinate reference system used for the project?
4. Make sure that 'Enable on the fly CRS transformation is checked.
5. Explore the properties for following coordinate systems: WGS 84, MGI/Balkans zone 5, MGI/Balkans zone 6, MGI/Balkans zone 7, ETRS89/ETRS-LAEA and ETRS89.
6. Find some of the above coordinate systems on [http://spatialreference.org](http://spatialreference.org), open them as 'Well Known Text as HTML' format and explore their properties.

---

**Task 2 – Saving data in different projection.**

Objective: Learn how to reproject data layer in other coordinate system.

**Steps to do:**

1. Open QGIS.
2. Load the required data layer located in data folder for 3-1 exercise.
3. This shape file represents Montenegro administrative border downloaded from [http://www.gadm.org/](http://www.gadm.org/).
4. What is the CRS of this shape file?
5. Now right click on the layer in layer panel and click 'Save As' - the new window will open where we can set up some new coordinate system for shape file.
6. For 'File name' choose new name for the new shape file and under 'CRS' click on the 'Select CRS' icon.
7. In 'Coordinate Reference System Selector' window find MGI/Balkans zone 6 and click OK.
8. What is the CRS of newly created shape file?

---

