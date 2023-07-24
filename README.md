# imdb_scraper
Jupyter Notebook to scrape imdb.com

1. Used Python (Jupiter Notebook) to scrape all movies from Jan 1, 1970 - April 30, 2023.
 - Scraped data is stored in .CSV files and broken up by groups of years.
   
2. x

## To do list
[ ] Edit _id to be unique in the dataset, not just the CSV  
[ ] Make a second pass using the imdb_url variable to pull box office and release details  
[ ] Merge the original dataset with the second pass dataset  
[ ] Edit the image_url to point to the large image  
[ ] Pull the large image to local hard drive (wget) and rename  
[ ] Include new image name in the CSV  
[ ] Merge all CSVs into single dataset  


## Records  
80,556 titles are returned and 100 titles are displayed on each page
https://www.imdb.com/search/title/?title_type=feature&release_date=1970-01-01%2C2023-04-30&countries=us&sort=release_date,desc&count=100&start=1
Keep records to be scraped below 10,000

- [x] 1970 --> 1970-01-01 : 1979-12-31 --> 3,542 titles  
- [x] 1980 --> 1980-01-01 : 1989-12-31 --> 4,120 titles   
- [x] 1990 --> 1990-01-01 : 1999-12-31 --> 8,692 titles   
- [x] 2000 --> 2000-01-01 : 2004-12-31 --> 6,148 titles   
- [x] 2005 --> 2005-01-01 : 2008-12-31 --> 7,459 titles  
- [x] 2009 --> 2009-01-01 : 2011-12-31 --> 8,457 titles  
- [x] 2012 --> 2012-01-01 : 2014-12-31 --> 9,925 titles  
- [x] 2015 --> 2015-01-01 : 2016-12-31 --> 7,217 titles  
- [x] 2017 --> 2017-01-01 : 2018-12-31 --> 7,889 titles  
- [x] 2019 --> 2019-01-01 : 2020-12-31 --> 7,330 titles  
- [x] 2021 --> 2021-01-01 : 2022-12-31 --> 8,621 titles  
- [x] 2023 --> 2023-01-01 : 2023-04-30 --> 1,167 titles


### URLs
_1970_url = 'https://www.imdb.com/search/title/?title_type=feature&release_date=1970-01-01%2C1979-12-31&countries=us&sort=release_date,desc&count=100&start='
_1980_url = 'https://www.imdb.com/search/title/?title_type=feature&release_date=1980-01-01%2C1989-12-31&countries=us&sort=release_date,desc&count=100&start='
_1990_url = 'https://www.imdb.com/search/title/?title_type=feature&release_date=1990-01-01%2C1999-12-31&countries=us&sort=release_date,desc&count=100&start='
_2000_url = 'https://www.imdb.com/search/title/?title_type=feature&release_date=2000-01-01%2C2004-12-31&countries=us&sort=release_date,desc&count=100&start='
_2005_url = 'https://www.imdb.com/search/title/?title_type=feature&release_date=2005-01-01%2C2008-12-31&countries=us&sort=release_date,desc&count=100&start='
_2009_url = 'https://www.imdb.com/search/title/?title_type=feature&release_date=2009-01-01%2C2011-12-31&countries=us&sort=release_date,desc&count=100&start='
_2012_url = 'https://www.imdb.com/search/title/?title_type=feature&release_date=2012-01-01%2C2014-12-31&countries=us&sort=release_date,desc&count=100&start='
_2015_url = 'https://www.imdb.com/search/title/?title_type=feature&release_date=2015-01-01%2C2016-12-31&countries=us&sort=release_date,desc&count=100&start='
_2017_url = 'https://www.imdb.com/search/title/?title_type=feature&release_date=2017-01-01%2C2018-12-31&countries=us&sort=release_date,desc&count=100&start='
_2019_url = 'https://www.imdb.com/search/title/?title_type=feature&release_date=2019-01-01%2C2020-12-31&countries=us&sort=release_date,desc&count=100&start='
_2021_url = 'https://www.imdb.com/search/title/?title_type=feature&release_date=2021-01-01%2C2022-12-31&countries=us&sort=release_date,desc&count=100&start='
_2023_url = 'https://www.imdb.com/search/title/?title_type=feature&release_date=2023-01-01%2C2023-04-30&countries=us&sort=release_date,desc&count=100&start='


## List data dictionary

| Header | Description |
| --- | ----------- |
| _id | Incremented ID uniquely identifying each record in an individual CSV file. |
| movie_title | Movie title |
| year | Year of the earliest release of this title globally. |
| mpaa_rating | Movie rating (G, PG, PG-13, R, etc.) |
| runtime | Length of movie (in minutes). |
| genre | Movie genre - The movie can belong to multiple genres. Each genre is separated by a comma. |
| rating | IMDb registered users can cast a vote on every title in the database that has been shown publicly at least once (including festival screening). Individual votes are then aggregated and summarized as a single IMDb rating The rating is between 1 and 10 and given to one decimal place. |
| metascore | The score of the movie on the metacritic website. Scores are on a scale of 0 - 100, with higher scores indicating better reviews. Scores are given by movie critics and the weighted score(based on the fame of the critic). The Metascore is a way to quickly get a sense of what the critical consensus is on a particular piece of media. |
| summary | Plot summary of movie. |
| director | Movie director(s)  |
| stars | Actors/actresses who starred in the movie. |
| votes | Number of user ratings for this title. |
| gross_revenue_us_canada | Lifetime gross revenue for title in US and Canada, in USD. |
| imdb_url | URL for movie details. |
| image_url | URL linking to the primary image associated with this movie. |

https://help.imdb.com/article/imdb/track-movies-tv/weighted-average-ratings/GWT2DSBYVT2F25SK#  




## Details data dictionary

| Header | Description |
| --- | ----------- |
| _id | incremented ID uniquely identifying each record in an individual CSV file. |
| imdb_url | URL for movie details. |
| aggregate_rating_score | Same as 'rating' in _list dataset |
| popularity_score | Calculated with IMDb algorithms.  The primary measure is who and what people are looking at on IMDb. The rankings are updated on a weekly basis, typically by the end of Monday. |
| release_date_us | When was the movie first released in teh US? |
| country_of_origin | Origin country of the movie. |
| also_known_as | Alternative title texts by which this title is also known. Limited to one. |
| estimated_budget | Estimated budget to create and release movie, in USD. |
| opening_weekend_domestic_date | Date movie premeiered in US and Canada |
| opening_weekend_domestic_gross | Opening weekend gross revenue in US and Canada,  in USD. |
| worldwide_gross | Lifetime gross revenue for title, worldwide, in USD. |
| image_url_big | URL for movie art set to 400 pixels. |

* domestic refers to US and Canada in this dataset.


## Notes  

https://m.media-amazon.com/images/M/MV5BNzg3OTEzMTgtYWU0OC00YTI0LWIxOTAtNmRkNTc0Nzg2YWU1XkEyXkFqcGdeQXVyNjY1MTg4Mzc@._V1_FMjpg_UX900_.jpg  <<<—— change everthing after the @ sign to this  
  
``` @._V1_FMjpg_UX400_.jpg ```
