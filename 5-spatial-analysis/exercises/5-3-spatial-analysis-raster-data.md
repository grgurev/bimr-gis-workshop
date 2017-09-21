## Data processing and handling techniques for the purposes of efficient biodiversity data management and reporting
### Exercise 5.3 - Spatial analysis - Raster data  
#### Objective - Learn how to create heat maps   

Document version: 2017-09-21  
Document author: Marin Grgurev, PhD  
Exercise author: Ujaval Gandhi

---

**Task 1: Creating heatmaps.**
Objective: Learn how to create heat maps

**Steps to do:**
1. Start new project in QGIS.
2. Go to Layer > Add Vector Layer and browse to the `data/cro-gbif-occurences.shp` file and click Open.
3. Zoom-in a bit closer to get a better look at the data. You will notice that the data is quite dense and it is hard to get an idea of where there is a high concentration of points. This is where a heatmap will come in handy so thatwe can have visual guidance where are the hotspots with most collected species.
4. If you need to create a heatmap for purely visual purpose or for printing - QGIS has a built-in symbology renderer called Heatmap. Let’s try that first. Right-click on the layer cro-gbif-occurences and select Properties.
5. In the Properties dialog, switch to the Style tab. Select Heatmap as the renderer. You have a lot of choice of color-ramps for the heatmap. Choose the Oranges color-ramp. Leave the other parameters to default and click OK.
6. You will see a nice heatmap of your data and pockets of heat where there is a high concentration of occurences. There are quite a few options available in the heatmap renderer to create the most appropriate visualization for your dataset. If you just wanted to create a heatmap for print or visual inspection - you are done! But we will explore another more powerful heatmap creation option where you can use the results in your analysis also.
7. Enable a core plugin named Heatmap. Once you have enabled the plugin, go to Raster > Heatmap > Heatmap.
8. In the Heatmap Plugin dialog, choose `species_heatmap` as the name for the Output raster. Enter `2000` meters as the Radius. Radius is the area around each point that will be used to calculate the *"heat"* a pixel received. Check the Advanced so we can specify the output size of our heatmap. Enter `2000` as Rows value. The Columns value will update automatically. Click OK to start the heatmap creation process.
9. Once the processing is finished, you will see a grayscale layer called `species_heatmap` loaded into the canvas. Uncheck the `cro-gbif-occurences` layer.
10. Let’s make our heatmap look more like the traditional heatmap similar to the earlier visualization. Right-click on the heatmap layer and click Properties.
11. In the Style tab, select Singleband pseudocolor as the Render type. Next, under the section Load min/max values check Min / Max and select the Estimate (faster) as the Accuracy and click Load. This will scan the heatmap and find the minimum and maximum pixel values. These values will be used to generate an appropriate color ramp. In the section Generate new color map, select YlOrRd (Yellow-Orange-Red) as the color ramp, and click Classify. Click OK.
12. Now you will see a more appealing heatmap-like rendering of the layer. You can select the Identify tool and click on any pixel of the heatmap. You will see the pixel value in the resulting pop-up. This pixel-value is a measure of how many points from the source layer are contained within the specified radius ( in our case - 2000 m) around the pixel.
13. Now you have your heatmap layer that can be saved for future use. Many times, you want to identify the hotspots where there is high-concentration of points. We will now try to identify such hotspots using this heatmap. Go to Raster > Raster Calculator.
14. You will have to decide on a threshold value first. All pixel values above that threshold will be considered to be in a cluster. Let’s use a value of 10 for this data. In Raster calculator dialog, name the output layer as `species_hotspots_vector`. Double-click on `species_heatmap@1` under the Raster bands section and it will be added to the Raster calculator expression text area. Complete the expression as shown below. Check the box next to Add result to project and OK. 
```
"species_heatmap@1" > 10
```
15. A new layer called `species_hotspots_vector` will be added to QGIS. This layer has pixels with values of either 0 or 1. All pixels in the input layer where the pixel value was larger than 10 now have a value of 1 and all remaining pixels are 0. Click on Raster > Conversion > Polygonize (Raster to Vector).
16. Make sure that as Input file `species_hotspots_vector` raster is selected. Name the output polygon file as `species_hotspots_vector`. Check the box next to Field name as well as Load into canvas when finished. Click OK.
17. Once the conversion finishes, you will have yet another layer named `species_hotspots_vector` added to QGIS. This is the vector representation of the clusters that were created in the previous step. The layers contain clusters with both 0 and 1 values. Let’s filter out the 0 values, so we get the clusters of hotspots. Right-click on the layer and select Open Attribute Table.
18. In the Attribute table, click on Select feature using an expression.
19. Enter the expression as shown below and click Select. Next, click on Close.
```
"DN" = 0
```
20. In the main attribute table window, you will see some features highlighted. These are the features that matched our query. Click the Toggle editing mode button in the toolbar and then click the Delete selected features (DEL) button.
21. Once the selected features are deleted, click the Save Edits button and then Toggle editing mode again to put the layer in read-only mode. Close the attribute table window.
22. In the main QGIS window, un-check the `species_hotspots` layer. The final layer `species_hotspots_vector` contains the cluster extracted from the heatmap. These clusters are the intelligence gathered from the raw data and can provide useful insights as well as serve as an input for further analysis.
