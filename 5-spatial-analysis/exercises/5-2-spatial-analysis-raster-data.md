## Data processing and handling techniques for the purposes of efficient biodiversity data management and reporting
### Exercise 5.2 - Spatial analysis - Raster data
#### Objective - Learn how to handle conduct basic raster analysis in QGIS
Document version: 2017-09-20
Document author: Marin Grgurev, PhD
Exercise author: Ujaval Gandhi

---

**Task 1: Sampling Raster Data using Points or Polygons.**
Objective: Learn how to sample raster data using points or polygons

**Steps to do:**
1. Start new project in QGIS.
2. Go to Layer > Add Raster Layer and browse to the `data/dem500.tif` file and click Open.
3. Once the layer is loaded, select the Identify tool and click anywhere on the layer. You will see the elevation value in meters as the value or Band 1 at that location.
4. Now go to Layer > Add Vector Layer and browse to the `data/cro-gbif-occurences.shp` file and click Open.
5. Now we are ready to extract the elevation values from the raster layer. Install the Point Sampling Tool plugin.
6. Open the plugin dialog from Plugins ‣ Analyses ‣ Point sampling tool.
7. In the Point Sampling Tool dialog, select `cro-gbif-occurences` as the Layer containing sampling points. We must explicitely pick the fields from the input layer that we want in the output layer. Choose *scientific* and from the `cro-gbif-occurences` layer. We can sample values from multiple raster band at once, but since our raster has only 1 band, choose the `cro-dem500 : Band 1` (raster). Name the output vector layer as `species_elevation.shp`. Click the OK to start the sampling process. Click Close once the process finishes. You can multiselect fields with Ctrl key.
8. You will see a new layer `species-elevation` loaded in QGIS. Use the Identify tool to click on any point to see the attributes. You will see `cro-dem5_1` field - which contains the raster pixel value at the location of the point.
9. First part of our analysis is over. Let’s remove the unnecessary layers. Hold the `Shift` key and select `species-elevation` and `cro-gbif-occurences` layers. Right-click and select Remove to remove them from QGIS TOC.
10. Go to Layer > Add Vector Layer. Browse to the `data/counties.shp` file and click Open.
11. A new layer named counties will be add to QGIS.
12. Enable the Zonal Statistics Plugins. This is a core plugin so it is already installed.
13. Go to Raster > Zonal statistics > Zonal statistics.
14. Select `cro-dem500` as the Raster layer and counties as the Polygon layer containing the zones. Enter *elev* Output column prefix. Click OK.
15. The analysis may take some time depending on the size of the dataset.
16. Once the processing finishes, select the counties layer. Use the Identify tool and click on any county polygon. You will see five new attributes added to the layer: `elev_count`, `elev_sum`, `elev_mean`, `elev_min` and `elev_max`. These attributes contain the count of raster pixels, sum of raster pixel, mean of raster pixel values and both minimimal and maximal values of raster pixel values respectively. Since we are interested in average temperature, the `elev_mean` field will be the one to use.
17. Let’s style this layer to create a elevation map. Right-click the `counties` layer and select Properties.
18. Switch to the Style tab. Choose Graduated style and select `elev_mean` as the Column. Choose a Color Ramp and Mode of your chose. Click to choose 10 classes. Click Classify to create the classes. Click OK.
19. You will see the county polygons styled using average elevation extracted from the raster grid. 
