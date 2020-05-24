## **Historical land use dynamics during conflict and onset of peace in the Colombian Andes-Amazon region**

Paulo J. Murillo-Sandoval, Emma Gjerdseth, Robert Kennedy, David Wrathall, and Jamon Van Den Hoek, Camilo Correa-Ayram, and Liliana M. Davalos.



### The problem

Practical use of remote sensing data form making historical land-use maps using well-known change detection algorithms remains poorly evaluated in peripheral countries. Furthermore, National agencies take between 2-3 years to produced land-use maps leading slow decision conservation initiatives, especially in areas historical affected by armed conflict. 

Here, we used spectral predictors from Landsat which were linearly fitted using LandTrendr to create maps for six classes:

**Urban, Pasture, Forest, Grasslands, Secondary Forest and Water.**

The process is very practical to be applied everywhere and more specifically in forested places in which political conditions might exacerbate land-use quick conversions.



## Results









### Scripts

1. We used LandTrendr to obtain linearly consistent spectral data for different vegetation indices from 1984-2019. We used NBR as a baseline index for segmentation and the vertex obtained were imposed over a set of spectral metrics. 

   **var ftvList = ['TCW', 'TCG', 'TCB', 'NBR', 'NDFI', 'NDVI','GV_NDFI','SOIL_NDFI','NPV_NDFI', 'NDMI', 'B1', 'B2', 'B3', 'B4', 'B5', 'B7'];**

 We initially removed bad Landsat images using a visual inspection using this code: https://code.earthengine.google.com/2edf4e85c9f471c42b987f5a6b60a8f9



After that we removed clouds using fmask, harmonization of Landsat sensors, applied a physical topographic correction, and eliminated Landsat data in an negative buffer of 2Km to avoid problems in the borders. We created annual composites using medoid method using all image within the year. Finally we applied LandTrendr to get fitted values across time, all the code that makes this process is here: https://code.earthengine.google.com/7d6901bc61883f1f4ada851e8fa7e7ab



Using that code, users can change your baseline index, the list of predictors and the time window i.e. January- March.  



2. The second script takes the annual asset created in step 1 and using a basemap in 2002 stratafied points in six classes. We also used another year to improve training. The code exports annual land-use maps for each year.

   

   

3. 

