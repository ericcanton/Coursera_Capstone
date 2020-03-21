# Coursera_Capstone
Repository used for the capstone course of the IBM Data Science Professional Certificate. 

There are two projects in this repository:
1. Week 3 of the capstone had us create a Jupyter Notebook that scrapes a table off of Wikipedia containing postal codes and neighborhood/borough names for Toronto. We then needed to choose some method of segmenting the neighborhoods using Foursquare data. I chose to do segmetation by density of coffee shops: given GPS coordinates of the neighborhood centers, I polled the Foursquare API for coffee shops within a 500 meter radius of those centers and divided the response into "local" and "chain" coffee (here meaning Starbucks, Tim Hortons, and Dunkin'). Finally, I used an Scikit-Learn's KMeans object, K=3, to segment the neighborhoods, then created an interactive map with Folium showing the neighborhoods, colored by segment, along with the local coffee shops found. 
2. Weeks 4 and 5 of the capstone revolve around the certification program's final project. We were given our choice of segmentation project, so long as it incorporates the Foursquare API. I chose to play the role of a data-mining real estate consultant helping a young couple move to a new city. Please see the README file, as well as <code>EC_segmentation.pdf</code>, <code>EC_pres.pdf</code>, and the Jupyter Notebook, in the Weeks_4_5 folder for more details.
