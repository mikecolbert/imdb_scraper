# imdb_scraper
Jupyter Notebook to scrape imdb.com

1. Used Python (Jupiter Notebook) to scrape all movies from Jan 1, 1970 - April 30, 2023.
 - Scraped data is stored in .CSV files and broken up by groups of years.
   
2. x

## To do list
[] Edit _id to be unique in the dataset, not just the CSV
[] Make a second pass using the imdb_url variable to pull box office and release details
[] Merge the original dataset with the second pass dataset
[] Edit the image_url to point to the large image
[] Pull the large image to local hard drive (wget) and rename
[] Include new image name in the CSV
[] Merge all CSVs into single dataset



## Data dictionary

| Header | Description |
| --- | ----------- |
| _id | incremented ID uniquely identifying each record in an individual CSV file |
| movie_title | Movie title |
| year | Year the movie was released |
| mpaa_rating | Movie rating (G, PG, R, etc.) |
| runtime | Length of movie (in minutes) |
| genre | Movie genre - The movie can belong to multiple genres. Each genre is separated by a comma. |
| rating | Movie rating by fans and critics |
| metascore | ??? |
| summary | Plot summary of movie |
| director | Movie director(s)  |
| stars | Actors/actresses who starred in the movie |
| votes | ??? |
| gross_revenue_us_canada | ??? |
| imdb_url | URL for movie details |
| image_url | URL for movie art |

