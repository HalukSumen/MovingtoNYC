<h1 align="center">Moving to New York City</h1>


<h2>INTRODUCTION</h1>

Moving another country is difficult, especially if you do not speak the local language.  Before I came to Rome in 2017, I had to find out an accommodation for my Master Degree. So, I have checked some neighborhoods for long-term stay. I had come one year ago, and I was somewhat aware about touristic locations. I had not known safer places, locations that are suitable for students, and the demographic features of neighborhoods. Starting from this observation, I wanted to create a restaurant guide for the newcomers. If number of specific restaurants are higher than any other type then it means, people who are living that location which means they came from that cuisine’s country. For example, in Salario neighborhood if number of French restaurants are high, it means there are possibly high number of French people living in that neighborhood. In the end, I would like to provide people who wants to live with people who are in same origin country or provide to avoid that.

<h2>PROBLEM</h1>
Moving another country is really hard thing for everyone, moreover, finding an adequate place is a time-consuming burden. For that reason, I would like to investigate restaurants because; If there is high number of same culture restaurants in small location it means, the people live there should be originally came from that culture. Solving this problem requires clustering because we must make groups of restaurants while they are in different locations. Also supervised, or reinforcement learning methods will not be effective in this situation because it is not possible to make assumptions in this problem. So, I am going to used Unsupervised Algorithm which will be K-Means.

<h2>DATA</h1>
I am going to use two different data sources, the first one is from New York University Spatial Data Repository which includes name of the boroughs, neighborhoods and latitudes and longitudes of neighborhoods. Data is public and can be accessible by anyone who wants [1]. The Second data source is Foursquare API, for collecting data you must register their system, however there are limits for both downloading data and the type of available data can reach. I choosed free version and can make 100.000 API calls daily. If you exceed that limit the call will not work until next day [2]. My two data sources are connected. My two data sources are connected and interrelated. Without NYU part, I cannot find which venue in which neighborhood and borough, without Foursquare part I cannot reach restaurants. NYU part contains 5 Boroughs and 306 Neighborhoods names and geolocations. Foursquare part contains 21.000 rows of venues, but I am going to use 4800 rows of restaurants. 

<p align="center">
  <img width="800" height="600" src="https://github.com/HalukSumen/MovingtoNYC/blob/main/images/top20rest.png">
</p>


<h2>METHODS</h1>

![Image](https://i.imgur.com/MGWahfo.png)
In the schema above, I visualized Data collecting and processing steps. Firstly, I will collect data from NYU and Foursquare, but in NYU part I will just use Borough and Neighborhood names and their geolocations, in Foursquare part I will use method to call Venue Name, Category and geolocations. In foursquare part, I will clean Category by restaurants. With number of restaurants, I will create frequency table for each restaurant type. Later creating frequency table, I will merge frequency table with my Data Frame 3. Lastly, I will merge Data Frame 3 and 4, and I will evaluate results which I will support with map visualization.

<h2>EVALUATION</h1>

K-Means is creating clusters but not deciding how many clusters will create. So, If I assign to number of clusters randomly, it may cause excessive or insufficient clusters and it will highly cause unmeaningful results. So, I cannot choose number of clusters randomly, for that I am going to Elbow Method to see and decide number of clusters and then I can expect meaningful results.

<p align="center">
  <img width="800" height="600" src="https://github.com/HalukSumen/MovingtoNYC/blob/main/images/elbowmethod.png">
</p>
<p align="center">
   <b>Elbow Method</b>
</p>

<p align="center">
  <img width="800" height="600" src="https://github.com/HalukSumen/MovingtoNYC/blob/main/images/silhoutte.png">
</p>
<p align="center">
   <b>Silhoutte Method</b>
</p>




<h2>RESULTS</h1>
In the end I am expecting to see, well clustered restaurants and observe meaningful results over the New York City neighborhoods.

<p align="center">
  <img width="800" height="600" src="https://github.com/HalukSumen/MovingtoNYC/blob/main/images/maincluster.png">
</p>
<p align="center">
   <b>Main Cluster</b>
</p>

<p align="center">
  <img width="600" height="600" src="https://github.com/HalukSumen/MovingtoNYC/blob/main/images/cluster0.png">
</p>
<p align="center">
   <b>Cluster 0</b>
</p>

<p align="center">
  <img width="600" height="600" src="https://github.com/HalukSumen/MovingtoNYC/blob/main/images/cluster1.png">
</p>
<p align="center">
   <b>Cluster 1</b>
</p>

<p align="center">
  <img width="600" height="600" src="https://github.com/HalukSumen/MovingtoNYC/blob/main/images/cluster2.png">
</p>
<p align="center">
   <b>Cluster 2</b>
</p>

<p align="center">
  <img width="600" height="600" src="https://github.com/HalukSumen/MovingtoNYC/blob/main/images/cluster3.png">
</p>
<p align="center">
   <b>Cluster 3</b>
</p>

<p align="center">
  <img width="600" height="600" src="https://github.com/HalukSumen/MovingtoNYC/blob/main/images/cluster4.png">
</p>
<p align="center">
   <b>Cluster 4</b>
</p>

<p align="center">
  <img width="600" height="600" src="https://github.com/HalukSumen/MovingtoNYC/blob/main/images/cluster5.png">
</p>
<p align="center">
   <b>Cluster 5</b>
</p>

<p align="center">
  <img width="600" height="600" src="https://github.com/HalukSumen/MovingtoNYC/blob/main/images/cluster6.png">
</p>
<p align="center">
   <b>Cluster 6</b>
</p>



<h2>LINKS</h1>

1. https://geo.nyu.edu/catalog/nyu_2451_34572
2. https://developer.foursquare.com/docs/places-api/rate-limits/
