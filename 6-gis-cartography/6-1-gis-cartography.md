## Data processing and handling techniques for the purposes of efficient biodiversity data management and reporting
### Exercise 5 - GIS cartography
#### Objective - Apply styles to layes and create maps.
Document version: 2017-09-14
Document author: Petra Štrbenac; Marin Grgurev, PhD

---

**Task 1: Apply simple symbology to layer.**

**Steps to do:**
1. Create new QGIS project and add the following shapefile data\BiogeoRegions2016.shp to your map.
2. Open the Properties window of Biogeographical regions layer and choose Tab Style where you can change the appearance of your layer.
3. Try changing the color of your layer. Try using the predefined styles and try creating your own.
4. Apply layer transparency.

---

**Task 2: Apply categorized styles to layer.**

**Steps to do:**
1. Create new QGIS project. Add clc2012_kosovo_wgs84 layer to your map. Drag and drop it on map from your vector_analysis.sqlite database.
2. Open the Properties window of clc2012_kosovo_wgs84 layer and choose Tab Style where you can change the appearance of your layer.
3. On the first dropdown menu on Style Tab select Categorized.
4. In the Column dropdown menu select "code_12" field.
5. Choose a color ramp of your choice and click Classify to get different symbols for each of CLC classes.
6. Click Apply to save changes.

---

**Task 3: Show lables for layers.**

**Steps to do:**
1. Create new QGIS project and add the following shapefile data\research_area.shp to your map.
2. Open the Properties window of Research areas layer and choose Tab Labels where you can change the appearance of labels for your data.
3. In the first dropdown menu on Labels tab choose "Show labels for this layer".
4. In the "Label with" dropdown choose the field which contains the values that you want to show as lables for your data. In this example the most appropriate filed to choose is "name".
5. Try changing the font, size and color of lable text.
6. Try adding background to your labels.

---

**Task 4. Create map for print.**

**Steps to do:**
1. Create new QGIS project and add the following shapefile data\BiogeoRegions2016.shp to your map.
2. Apply Categorized styles for your layer. Categorize styles by "code" field.
3. Add lables for Biogeographical regions layer.
4. Now you can start to assemble your map for print. Go to Project ‣ New Print Composer.
5. You will be prompted to enter a title for the composer. You can leave it empty and click Ok.
6. In the Print Composer window, click on "Zoom full" icon to display the full extent of the Layout.
7. Now we would have to bring the map view that we see in the QGIS Canvas to the composer. Go to Layout ‣ Add Map. Select Layout ‣ Move item content to pan the map in the window and center it in the composer.
8. Add legend by clicking Layout - Add legend.
9. Try adding scale bar.
10. Try adding the North Arrow. The Print Composer comes with a nice collection of map-related images - including many types of North Arrows. Click Layout ‣ Add Image. Holding your left mouse button, draw a rectangle on the top-right corner of the map canvas. On the right-hand panel, click on the Item Properties tab and expand the Search directories section and select the North Arrow image of your liking.
11. Once you are satisfied with the map, you can export it as Image, PDF or SVG. For this tutorial, let’s export it as an image. Click Composer ‣ Export as Image.
