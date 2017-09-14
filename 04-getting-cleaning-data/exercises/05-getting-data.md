## Data processing and handling techniques for the purposes of efficient biodiversity data management and reporting
### Exercise 5 - Getting data (data acquisition)
#### Objective - Obtain GIS and related data from various online sources
Document version: 2017-09-14
Document author: Petra Štrbenac; Marin Grgurev, PhD

---

**Task 1: Acquire data from online sources.**
Objective: Fetch GIS data on species occurrences for your country from GBIF Portal.

**Steps to do:**
1. Go to GBIF Portal. Search for it on the Internet.
2. Choose to search Occurrences.
3. Filter data to include only records for your country.
4. Register as new user. Verify registration and login.
5. Download data in CSV format.

---

**Task 2: Use PESI EU Nomen Taxon Match Service.**
Objective: Match and compare list of species with PESI EU Nomen Catalogue of species.

**Steps to do:**
1. Search for Taxon Match service on PESI EU Nomen portal.
2. Choose a file located in \data\species_list.csv.
3. Make sure to check First row contains column names.
4. Choose the following fields as output: GUID, ScientificName, Authority, Accepted name, Taxon status

---

**Task 3: Retrieve GIS data from WMS/WFS Web Service.**
Objective: Connect to WMS/WFS Web Service using QGIS.

1. Search for GIS data on Biogeographical regions that you can get via WMS web service. You can search for available services on EEA DiscoMap Portal.
2. Check Biogeographical regions description data to discover WMS URL.
3. Open QGIS. In Browser panel, navigate to WMS and choose New connection (right click on WMS).
4. In the “Create a new WMS connection” windows, enter connection name (choose you own) and paste URL from step 3 to URL field. Click Connect to establish a connection to this web map service.
5. In the Browser panel navigate to WMS and find your new WMS connection. Click on the + sign next to the connection name and observe the available data layers.
6. Drag and drop Biogeographical region layer to the Layer panel to display it on map.
