# Data Wrangling Steps for Capstone 1: 
_Amazon Rating Predictor_

## Book review data description
Consumer reviews and ratings. I have a dataset of over 22 million book reviews from Amazon.com from May 1996 - July 2014. These reviews are made available by Julian McAuley UCSD professor of Computer Science (McAuley et al. 2015; He & McAuley 2016). For this project, I will utilize a subset of all book reviews within two specific categories to train and test the algorithm. 
  * J. McAuley’s main page: http://cseweb.ucsd.edu/~jmcauley/
  * Amazon Review Data links: http://jmcauley.ucsd.edu/data/amazon/  Data files with all reviews are only available from Julian McAuley by request.
  * Metadata file from J. McAuley, with permission.
  * Count of reviews_Books records: 22507155
  * Count of 5.0 rated reviews: 13886788
  * Count of MetaData records: 9430088
  * For books with 10-digit International Standard Book Number (ISBN), the ASIN and the ISBN are the same.

## Steps to access book review data
Because the book reviews json file is almost 20 GB I cannot open it with Jupyter Notebook. Instead I installed MongoDB and Studio 3T to access the json as a database file. Then, in Jupyter Notebook with PyMongo I can extract the reviews I want to use (within a genre) for the Machine Learning algorithms.
[insert code snippets?]

## Additional data to augment review data
Because the book review data includes ASIN codes, but no title or genre information we need additional book data in order to subset the large review data base into genre sets for the Machine Learning, Natural Language Processing goal of the Capstone.
Google Books API query for Invertebrate Biology textbooks with API key masked: 

https://www.googleapis.com/books/v1/volumes?q=science+biology+invertebrate+nonfiction&maxResults=10&startIndex=0&printType=books&subject:textbook&key=xxxxxx


The results of this query are nested JSON with nested objects and arrays. To access the key:value pairs of interest I used I have coded my API query in Jupyter Notebook with 'requests.get' and I have used 'json_normalize' from pandas.io.json to flatten the nested json from the API. 
[insert code]

In addition, 

