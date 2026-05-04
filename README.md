# ArcGIS Portfolio

This portfolio includes examples of the work I've done with ArcGIS. Currently, it primarily includes maps made as part of my coursework for my GIS with a Concentration in Environmental Analysis Certificate from San Francisco State University, as well as an example of a project from my Introduction to GIS and GPS for Scientists course from University of California, San Diego.

## Cartographic Design for GIS (SFSU)

The following maps were created in ArcGIS Pro as part of a course on the principles of cartographic design. We discussed how to use map layout, map elements, data symbolization, color schemes, and figure/ground relationships to effectively communicate meaning to intended audiences.

<img src="/Assets/Farallon Island Plants Final.jpg" width="800"> <img src="/Assets/Africa City Growth Final.jpg" width="500"> <img src="/Assets/Meadow Restoration Study Sites.jpg" width="800"> <img src="/Assets/Oregon Map.jpg" width="800">

## Spatial Analysis and Modeling (SFSU)

This course was an overview of the concepts and functions used in vector-based spatial analysis within ArcGIS Pro.

### Modeling Landslide Risk

The final project for this course involved using ModelBuilder to create a map displaying landslide risk. We used an example data set that consisted of geology, land cover, and slope (each with their own polygon feature class) for a portion of San Mateo County, California. First, the different types of geology were each assigned a weight based on their stability, the types of land cover were assigned weights based on their vegetation density, and the different slopes were assigned weights based on their steepness. All of these weights were combined to create an index for landslide risk, with higher values meaning higher risk.

| Geology  | Stability  | Stable_wt  |
| ------------------------ | ----------------- | --------- |
| unknown  | X  | -9  |
| coarse alluv. fan  | unstable  | 2  |
| plastic silt/silty clay  | medium stability  | 1  |
| alluvium  | unstable  | 2  |
| sand  | unstable  | 2  |
| sand/gravel  | unstable  | 2  |
| bay mud  | unstable  | 2  |
| conglomerate  | medium stability  | 1  |
| sandstone  | medium stability  | 1  |
| mudstone/shale  | medium stability  | 1  |
| graywacke  | medium stability  | 1  |
| chert  | medium stability  | 1  |
| granite  | stable  | 0  |
| basalt  | stable  | 0  |
| felsic volcanics  | stable  | 0  |
| schist  | medium stability  | 1  |
| greenstone  | medium stability  | 1  |
| serpentinite  | medium stability  | 1  |
| marble/limestone  | stable  | 0  |
| artificial fill  | unstable  | 2  |
| water  | X | -9  |

| Veg_Type  | Density  | Density_wt  |
| ------------------------- | ------- | ---------- |
| Annual Grassland  | Sparse  | 1  |
| Closed-Cone Pine-Cypress  | Dense  | 0  |
| Coastal Oak Woodland  | Sparse  | 1  |
| Coastal Scrub  | Sparse  | 1  |
| Cropland  | Sparse  | 1  |
| Doughlas-Fir  | Dense  | 0  |
| Eucalyptus  | Dense  | 0  |
| Lacustrine  | Other  | -9  |
| Mixed Chaparral  | Sparse  | 1  |
| Montane Hardwood  | Sparse  | 1  |
| Redwood  | Dense  | 0  |
| Urban  | Sparse  | 1  |

| Percent_Slope  | Steep  | Steep_wt  |
| -------------- | ------ | --------- |
| 0  | Flat  | -9  |
| 4  | Flat  | -9  |
| 10  | Flat  | 0  |
| 25  | Flat  | 2  |
| 50  | Steep  | 3  |
| 100  | Steep  | 4  |
| 10000  | Steep  | 5  |

Second, ModelBuilder was used to lay out the next steps of the model-making process in order. The three polygon feature classes were combined with Union, unnecessary fields were removed, and the weight fields were joined to the main table. A slide index field was created, filled with default values, and then calculated for features with no null values by adding together the three weight values.

<img src="/Assets/Landslide Model.svg" width="1000">

Finally, the polygons of the output feature class were dissolved and symbolized based on their slide index values. For the sake of readability, some of the slide index values that had very few polygons representing them were grouped together.

<img src="/Assets/Landslide Risk Map.jpg" width="500">

## Introduction to GIS and GPS for Scientists (UCSD)

For the final project of this course, my two group members and I worked to create an ArcGIS StoryMap with an incorporated web map to share the locations of public fruit trees around UC San Diego.

### Survey123

One group member and I worked together to create a survey intended to be filled out on your phone when you wanted to share the location and information on a publicly accessible fruit tree. You can view the full survey [here](https://survey123.arcgis.com/share/1773b261fa874580b1c607a44dd8bbd0).

<img src="/Assets/survey1.png" height="300"> <img src="/Assets/survey2.png" height="300"> <img src="/Assets/survey3.png" height="300"> 

### Web Map

As the basis for the StoryMap, I created an ArcGIS web map to automatically compile and display the submissions for our survey. Each point is colored according to the type of tree and clicking on a point pops up an info box with a table of the relevant survey information as well as a photo of the tree. You can view the full web map [here](https://www.arcgis.com/apps/mapviewer/index.html?webmap=00576c04264a4d9190a3b273b1507e1f&extent=-117.262,32.8622,-117.1986,32.8931).

<img src="/Assets/webmap1.png" height="420"> <img src="/Assets/webmap2.png" height="350"> <img src="/Assets/webmap3.png" height="350">

### StoryMap

Our final product for this project was our StoryMap, which I largely wrote the text, gathered the images, and created the layout for based on input from my group members. In addition to incorporating our survey and web map, it describes the purpose of our project and provides resources for connecting with community gardening projects around UC San Diego. You can view the full StoryMap [here](https://storymaps.arcgis.com/stories/94a426de683d4fd2b64298627344ea98).

<img src="/Assets/storymap1.png" width="800"> <img src="/Assets/storymap2.png" width="800"> <img src="/Assets/storymap3.png" width="800"> <img src="/Assets/storymap4.png" width="800">

