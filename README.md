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

| name                                              | year | rating | cast                                                                                                                                                                    | director              | genre                             | votes   | runTime |
|:---------------------------------------------------:|:------:|:--------:|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:-----------------------:|:-----------------------------------:|:---------:|:---------:|
| The Shawshank Redemption                          | 1994 | 9.2    |  Tim Robbins,  Morgan Freeman,  Bob Gunton,  William Sadler,  Clancy Brown,  Gil Bellows,  Mark Rolston,  James Whitmore,  Jeffrey DeMunn,  Larry Brandenburg           |  Frank Darabont       | Drama                             | 2560535 | 2:22:00 |
| The Godfather                                     | 1972 | 9.2    |  Marlon Brando,  Al Pacino,  James Caan,  Richard S. Castellano,  Robert Duvall,  Sterling Hayden,  John Marley,  Richard Conte,  Al Lettieri,  Diane Keaton            |  Francis Ford Coppola | Crime, Drama                      | 1762507 | 2:55:00 |
| The Dark Knight                                   | 2008 | 9      |  Christian Bale,  Heath Ledger,  Aaron Eckhart,  Michael Caine,  Maggie Gyllenhaal,  Gary Oldman,  Morgan Freeman,  Monique Gabriela Curnen,  Ron Dean,  Cillian Murphy |  Christopher Nolan    | Action, Crime, Drama, Thriller    | 2520896 | 2:32:00 |
| The Godfather: Part II                            | 1974 | 9      |  Al Pacino,  Robert Duvall,  Diane Keaton,  Robert De Niro,  John Cazale,  Talia Shire,  Lee Strasberg,  Michael V. Gazzo,  G.D. Spradlin,  Richard Bright              |  Francis Ford Coppola | Crime, Drama                      | 1220462 | 3:22:00 |
| 12 Angry Men                                      | 1957 | 9      |  Martin Balsam,  John Fiedler,  Lee J. Cobb,  E.G. Marshall,  Jack Klugman,  Edward Binns,  Jack Warden,  Henry Fonda,  Joseph Sweeney,  Ed Begley                      |  Sidney Lumet         | Crime, Drama                      | 756429  | 1:36:00 |
| Schindler's List                                  | 1993 | 8.9    |  Liam Neeson,  Ben Kingsley,  Ralph Fiennes,  Caroline Goodall,  Jonathan Sagall,  Embeth Davidtz,  Malgorzata Gebel,  Shmuel Levy,  Mark Ivanir,  Béatrice Macola      |  Steven Spielberg     | Biography, Drama, History         | 1305602 | 3:15:00 |
| The Lord of the Rings: The Return of the King     | 2003 | 8.9    |  Noel Appleby,  Ali Astin,  Sean Astin,  David Aston,  John Bach,  Sean Bean,  Cate Blanchett,  Orlando Bloom,  Billy Boyd,  Sadwyn Brophy                              |  Peter Jackson        | Action, Adventure, Drama, Fantasy | 1763111 | 3:21:00 |
| Pulp Fiction                                      | 1994 | 8.9    |  Tim Roth,  Amanda Plummer,  Laura Lovelace,  John Travolta,  Samuel L. Jackson,  Phil LaMarr,  Frank Whaley,  Burr Steers,  Bruce Willis,  Ving Rhames                 |  Quentin Tarantino    | Crime, Drama                      | 1966965 | 2:34:00 |
| The Lord of the Rings: The Fellowship of the Ring | 2001 | 8.8    |  Alan Howard,  Noel Appleby,  Sean Astin,  Sala Baker,  Sean Bean,  Cate Blanchett,  Orlando Bloom,  Billy Boyd,  Marton Csokas,  Megan Edwards                         |  Peter Jackson        | Action, Adventure, Drama, Fantasy | 1784969 | 2:58:00 |
| The Good, the Bad and the Ugly                    | 1966 | 8.8    |  Eli Wallach,  Clint Eastwood,  Lee Van Cleef,  Aldo Giuffrè,  Luigi Pistilli,  Rada Rassimov,  Enzo Petito,  Claudio Scarchilli,  John Bartha,  Livio Lorenzon         |  Sergio Leone         | Adventure, Western                | 737304  | 2:58:00 |

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
