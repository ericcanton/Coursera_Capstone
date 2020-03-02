# Data Description 

We will need some home listing data, so we will use BeautifulSoup and a headless Firefox server to scrape some house listings. Then, we will poll the Foursquare API looking for bookstores, coffee shops, and also some general explore calls to estimate densty of venues. 

We will download the first page from Trulia.com, and then locate the home listings using BeautifulSoup. We need to scrape the physical addresses out of the listings and get GPS coordinates for them. We'll also collect prices, beds/baths, and hold onto the web address of the listing for later plotting on a Folium map. 

## In-progam data storage

The house listings we will store in objects of a Python class we'll make, Listing, which has members:
* addr (street address)
* ll (latitude/longitude) 
* price
* beds
* baths
* sqft (square footage of the house)
* web (link address to the Trulia listing page) 

We will also make a Venue class, which has members:
* name 
* type (e.g. Church, Coffee Shop)
* ll
* web (address) 

## Data Collection 
1. We will use <code>selenium.webdriver.Firefox</code>, running in headless mode, to get the HTML file for Eau Claire house listings on Trulia. These GET requests return 30 listings per page, so we'll get 2 pages. 
2. The page source we will pass to BeautifulSoup to aid our parsing of the contents of that page.
3. Calling the <code>find_all</code> method of our soup object, we can easily find the physical and web addresses of listings. Looking closer at link text, this actually contains the prices, bed/bath count, and square footage, so we will scrape this info out while processing web addresses. The physical addresses are easier to get by locating appropriate div tags.
4. Once we have the info about each listing loaded into our Listing objects, we'll ask Foursquare for some local venue information. 
  * Coffee shops
  * Libraries
  * Book stores
  * Parks
  * Schools
5. Finally, we will pass some "explore" requests to Foursquare, using the response to investigate the areas with dense and sparse venues. These, along with the listings from the previous item,  will be used to rate the "venue density". 

## Data reporting
The primary means of presenting the gathered data to the client will be through a Folium map. The map will have the Listing objects plotted, with HTML tags including the information from Listing member variables. These will be attached to CircleMarkers, colored according to our evaluation of the property as "Good" (green), "Consider" (yellow), and "Avoid" (red). These categories will be formed via unsupervised DBSCAN learning, obtained from Scikit-Learn's OPTICS algorithm. 

The advantage of presenting the analysis of Eau Claire homes in this way is that the maps are interactive, and are a very familiar format based on pervasive use of Google maps. 
