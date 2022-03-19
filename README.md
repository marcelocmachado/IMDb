# IMDb Web Scraping & EDA
#### _*Marcelo de Campos Machado*_

![alt_text](https://static.amazon.jobs/teams/53/images/IMDb_Header_Page.jpg?1501027252)

### _DISCLAIMER: the code in this document is NOT intended for commercial purposes or for distribution. This is ONLY a Web Scraping practice. The data is property of IMDb._

## INTRO

## WEB SCRAPING

Web scraping is the process of extracting data from a website in an automated way. In most cases, web scraping is not a simple task. Websites come in different structures, with many shapes and forms and, as a result, web scrapers vary in functionality and features.

The simplest form of web scraping is manually copying and pasting data from a web page into a text file or spreadsheet. However, when you’re harvesting a large amount of data, this process can take too long.

The data for this article was refers to a movie database called IMDb. The scraping was performed with R, utilizing the package _**‘rvest’**_.

The web scraping code can be found in the following link:

> [Web Scraping Code](https://github.com/marcelocmachado/IMDb/blob/main/scrapingCode.md) 


## EXPLORATORY DATA ANALYSIS

### FORMATTING DATA

The table below shows the result the first ten rows of the scraping result. Some formatting and changes have to be made to make the further analysis easier.

| name                                              | year | rating | cast                                                                                                                                                                    | director              | genre                             | votes   | runTime |
|:---------------------------------------------------:|:------:|:--------:|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:-----------------------:|:-----------------------------------:|:---------:|:---------:|
| The Shawshank Redemption                          | 1994 | 9.2    |  Tim Robbins,  Morgan Freeman,  Bob Gunton,  William Sadler,  Clancy Brown,  Gil Bellows,  Mark Rolston,  James Whitmore,  Jeffrey DeMunn,  Larry Brandenburg           |  Frank Darabont       | Drama                             | 2560535 | 2:22:00 |
| The Godfather                                     | 1972 | 9.2    |  Marlon Brando,  Al Pacino,  James Caan,  Richard S. Castellano,  Robert Duvall,  Sterling Hayden,  John Marley,  Richard Conte,  Al Lettieri,  Diane Keaton            |  Francis Ford Coppola | Crime, Drama                      | 1762507 | 2:55:00 |
| The Dark Knight                                   | 2008 | 9      |  Christian Bale,  Heath Ledger,  Aaron Eckhart,  Michael Caine,  Maggie Gyllenhaal,  Gary Oldman,  Morgan Freeman,  Monique Gabriela Curnen,  Ron Dean,  Cillian Murphy |  Christopher Nolan    | Action, Crime, Drama, Thriller    | 2520896 | 2:32:00 |
| The Godfather: Part II                            | 1974 | 9      |  Al Pacino,  Robert Duvall,  Diane Keaton,  Robert De Niro,  John Cazale,  Talia Shire,  Lee Strasberg,  Michael V. Gazzo,  G.D. Spradlin,  Richard Bright              |  Francis Ford Coppola | Crime, Drama                      | 1220462 | 3:22:00 |
| 12 Angry Men                                      | 1957 | 9      |  Martin Balsam,  John Fiedler,  Lee J. Cobb,  E.G. Marshall,  Jack Klugman,  Edward Binns,  Jack Warden,  Henry Fonda,  Joseph Sweeney,  Ed Begley                      |  Sidney Lumet         | Crime, Drama                      | 756429  | 1:36:00 |

Access the link below to check the code for formatting:

> [Web Scraping Code](https://github.com/marcelocmachado/IMDb/blob/main/formattingCode.md) 

After getting the data prepared, let's move to the analysis!

### TOP RATINGS

The following plot shows the Top 10 movies with the highest ratings:

![Screenshot](/plots/plot_topRatings.png)

> _**The Sawshank Redemption**_ and _**The Godfather**_ feature at the top of the list with a rating of 9.2/10. Next, The Godfather: Part II, The Dark Knight and 12 Angry man follow the top 2 with a rating of 9/10.

### TOP VOTES

Are the highest rated movies at the top because they received more votes? Let's check it out.

![Screenshot](/plots/plot_topVotes.png)

> _**The Sawshank Redemption**_ has the highest amount of votes, totaling 2.56 million votes. Not all Top 10 rated movies figure in the Top 10 most voted movies.

### MOST FREQUENT GENRES

Next, we're going to analyze the most popular genre among the Top 250 Movies.

![Screenshot](/plots/plot_topGenres.png)

> _**Drama**_ is by far the most popular genre. It appears on 182 of the 250 movies. A movie can have more than one genre and 73% of them have the _'Drama'_ genre label. Following _Drama_, _Adventure_ (60), _Thriller_ (54), _Crime_ (51) and _Action_ (49) complete the Top 5 genres.

### MOST POPULAR GENRE COMBINATION

_Drama_ might be the most popular genre by itself. But what are the most popular _**combination of genres**_? Let's check it out:

![Screenshot](/plots/plot_topCombos.png)

> _**Crime and Drama**_ combined figure at the top, with **13** appearences. Drama and War (8), and Crime, Drama, Mystery and Thriller (7) are also popular combinations.

### MOST FREQUENT DIRECTORS

A film director manages the creative aspects of the production. They direct the making of a film by visualizing the script while guiding the actors and technical crew to capture the vision for the screen. They control the film’s dramatic and artistic aspects.

The next plot shows the most frequent directors in the Top 250 Movies

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
