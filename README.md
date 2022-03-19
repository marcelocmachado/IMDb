# IMDb Web Scraping & EDA
#### _*Marcelo de Campos Machado*_

![alt_text](https://static.amazon.jobs/teams/53/images/IMDb_Header_Page.jpg?1501027252)

### _DISCLAIMER: the code in this document is NOT intended for commercial purposes or for distribution. This is ONLY a Web Scraping practice. The data is property of IMDb._

## WEB SCRAPING

Web scraping is the process of extracting data from a website in an automated way. In most cases, web scraping is not a simple task. Websites come in different structures, with many shapes and forms and, as a result, web scrapers vary in functionality and features.

The simplest form of web scraping is manually copying and pasting data from a web page into a text file or spreadsheet. However, when you’re harvesting a large amount of data, this process can take too long.

The data for this article was refers to a movie database called IMDb. The scraping was performed with R, utilizing the package _**‘rvest’**_.

The web scraping code can be found in the following link:

> [Web Scraping Code](https://github.com/marcelocmachado/IMDb/blob/main/scrapingCode.md) 


## EXPLORATORY DATA ANALYSIS

### FORMATTING DATA

### Displaying Top 10 Rated Movies Table

### TOP RATINGS
![Screenshot](/plots/plot_topRatings.png)

### TOP VOTES
![Screenshot](/plots/plot_topVotes.png)

### MOST FREQUENT GENRES
![Screenshot](/plots/plot_topGenres.png)

### MOST POPULAR GENRE COMBINATION
![Screenshot](/plots/plot_topCombos.png)

### MOST FREQUENT YEARS


### MOST FREQUENT DIRECTORS
![Screenshot](/plots/plot_topDirectors.png)

### MOST FREQUENT ACTORS
![Screenshot](/plots/plot_topActors.png)

### AVG RATING BY DECADE
![Screenshot](/plots/plot_avgRatDecade.png)

### AVG RUNTIME BY DECADE
![Screenshot](/plots/plor_avgRunDecade.png)

### AVG RATING FOR TOP ACTORS
![Screenshot](/plots/plot_avgRatActors.png)

### AVG RATING FOR TOP DIRECTORS
![Screenshot](/plots/plot_avgRatDirect.png)

### RUNTIME DENSITY
![Screenshot](/plots/plot_FreqRunTime.png)

### RATING DENSITY
![Screenshot](/plots/plot_FreqRatings.png)

```r
some code

data = aggregate(bla,bla,FUN=bla)
```
