# Flood Mapping_Sentinel-4-Africa-DRR
<img src="https://uni-bonn.sciebo.de/s/XjjZLJ9uB4aaPJs/download" width="1000"/>


# Optical-based Flood Mapping

***

The objective of this notebook  is to determine the extent of flooded areas using Sentinel-2 optical satellite imagery. The use of Sentinel imagery provides a quick assessment of the flood extent. The processing of Sentinel-2 satellite imagery is simple to process to delienate water surfaces from other land covers. In this notebook, the most common approach; tresholding, is applied to map flooded land surfaces from non flooded. A major limitation to the use of Sentinel 2 optical data remains to be cloud cover especially during adverse weather conditions which is when flood events are common.

***

***Work Flow***  
The Jupyter Notebook begins first by importing the required libraries. The next step will involve generation of an Area of Interest*'(AOI)'* with the current version, the user is required to defined the upper left and lower right coordinates of the bounding box which is then used to create a geojson file of the boundary. Sentinel 2 image scenes covering the AOI are then queried from <a href="https://scihub.copernicus.eu/">Copernicus Open Access Hub</a> with the help of *'SentinelSat API'*. The resulting scenes from the query are then stored in an iterable list. The user can then visualize the scenes in a map using *'Folium'* library. 

The identified scene is then downloaded into the working directory and unzipped. The unzipped image with *'.SAFE'* is read using the *Eoreader* library which also computes the Normalized Difference Water Index(NDWI).
A global treshold is applied on the computed NDWI and the image is binarized to separate water and non-water pixels. The binarized image is then written to a folder.

<img src="https://uni-bonn.sciebo.de/s/MhwRRkpp1lyfjME/download" width="1000"/>



***Limitations***  
1.The notebook takes all the scenes that intersect the AOI, but for the processing it can inly process one scene at a time, the user has to choose the scene of interest using an index.

2.The user has to enter an AOI using absolute coordinates

3.The treshold used for separating water and non-water surfaces is a global treshold, a local treshold can be used for better performance


***

