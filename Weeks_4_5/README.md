## Segmentation analysis of Trulia listings in Eau Claire, WI

For my final project of the IBM Data Science Professional Certification through Coursera, I decided to perform segmentation analysis of Trulia homes for sale. 

I semi-invented a scenario where a young couple are moving to Eau Claire this summer and are looking to buy a home. Given some constraints and wishes from the clients, I used machine learning to cluster the houses according to total density of venues and also density of several categories of venue of interest to the "clients." You can read my techniques in <code>EC_segmentation.pdf</code>

* <code>Eau_Claire_Project.ipnyb</code> is the Jupyter Notebook associated with this scraping and ML segmentation, using K-means and OPTICS. 
* <code>EC_segmentation.pdf</code> is the report on my analysis: describing the business problem, data requirements and methods for obtaining and manipulating this data, methodology of analysis (which ML techniques I used, how, and why), and also some recommendations/conclusions.
* <code>EC_pres.pdf</code> is a slide presentation that I imagine giving to the clients once our analysis is complete. There are several PDF "pages" per slide, so be sure to view this in "Presentation" mode in your PDF viewer. 
* <code>Density.html</code> and <code>Venues.html</code> are the Folium maps produced as part of the analysis. The housing listings are color-coded based on the ML clustering, and links to the listings are provided in the popups.
* I typeset the PDFs for this project using LaTeX, and I've also included the source code for those. 
