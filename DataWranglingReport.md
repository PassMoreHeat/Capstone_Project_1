# Data Wrangling Steps for Capstone 1: 
_Amazon Rating Predictor_

## Book review data description
* Count of reviews_Books records: 22507155
* Count of 5.0 rated reviews: 13886788
* Count of MetaData records: 9430088
* For books with 10-digit International Standard Book Number (ISBN), the ASIN and the ISBN are the same.

## Steps to access book review data

## Additional data to augment review data
Becasue the book review data includes ASIN codes, but no title or genre information we need additional book data in order to subset the large review data base into genre sets for the Machine Learning, Natural Language Processing goal of the Capstone.
Google Books API query for Invertebrate Biology textbooks with API key masked: https://www.googleapis.com/books/v1/volumes?q=science+biology+invertebrate+nonfiction&maxResults=10&startIndex=0&printType=books&subject:textbook&key=xxxxxx
The results of this query are nested JSON with nested objects and arrays. To access the key:value pairs of interest I used I have coded my API query in Jupyter Notebook with 'requests.get' and I have used 'json_normalize' from pandas.io.json to flatten the nested json from the API. 
