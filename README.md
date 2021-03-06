# IMDb Web Scraping & EDA
#### _*Marcelo de Campos Machado*_

![alt_text](https://static.amazon.jobs/teams/53/images/IMDb_Header_Page.jpg?1501027252)

### _DISCLAIMER: the code in this document is NOT intended for commercial purposes or distribution. This is ONLY a Web Scraping practice. The data is property of IMDb._

## INTRO

The Internet Movie Database, as known as IMDb, is an online database of information related to movies and TV shows – including cast, production crew and personal biographies, plot summaries, trivia, ratings, and fan and critical reviews. :movie_camera: :clapper:

This article's objective is to analyze the Top 250 rated movies, according to users, and find out patterns among them.

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

> [Formatting Code](https://github.com/marcelocmachado/IMDb/blob/main/formattingCode.md) 

After getting the data prepared, let's move to the analysis! :bar_chart: :chart_with_upwards_trend:

### TOP RATINGS

The following plot shows the Top 10 movies with the highest ratings:

![Screenshot](/plots/plot_topRatings.png)

> _**The Sawshank Redemption**_ and _**The Godfather**_ feature at the top of the list with a rating of **9.2/10**. Next, The Godfather: Part II, The Dark Knight and 12 Angry man follow the top 2 with a rating of 9/10.

### TOP VOTES

Are the highest rated movies at the top because they received more votes? Let's check it out.

![Screenshot](/plots/plot_topVotes.png)

> _**The Sawshank Redemption**_ has the highest amount of votes, totaling **2.56 million** votes. Not all Top 10 rated movies figure in the Top 10 most voted movies.

### MOST FREQUENT GENRES

Next, we're going to analyze the most popular genre among the Top 250 Movies.

![Screenshot](/plots/plot_topGenres.png)

> _**Drama**_ is by far the most popular genre. It appears on **182** of the 250 movies. A movie can have more than one genre and 73% of them have the _'Drama'_ genre label. Following _Drama_, _Adventure_ (60), _Thriller_ (54), _Crime_ (51) and _Action_ (49) complete the Top 5 genres.

### MOST POPULAR GENRE COMBINATION

_Drama_ might be the most popular genre by itself. But what are the most popular _**combination of genres**_? Let's check it out:

![Screenshot](/plots/plot_topCombos.png)

> _**Crime and Drama**_ combined figure at the top, with **13** appearences. Drama and War (8), and Crime, Drama, Mystery and Thriller (7) are also popular combinations.

### MOST FREQUENT DIRECTORS

A film director manages the creative aspects of the production. They direct the making of a film by visualizing the script while guiding the actors and technical crew to capture the vision for the screen. They control the film’s dramatic and artistic aspects.

The next plot shows the most frequent directors in the Top 250 Movies:

![Screenshot](/plots/plot_topDirectors.png)

> There are five directors tied at the top of the list: _**Steven Spielberg, Stanley Kubrick, Martin Scorsese, Christopher Nolan**_ and _**Akira Kurosawa.**_

### MOST FREQUENT ACTORS

Casting is one of the most crucial parts of the filmmaking process because the actors' performances can significantly impact how audiences and critics receive a film. Choosing the right actor can enhance your project, while a miscast role can diminish a particular character’s believability, which can be detrimental to a film or TV show. Even if the character is unlikeable or an antihero, the audience must believe the actor’s performance to remain invested. Finding the right talent for a role can be challenging because it requires a mix of critical analysis, instinct, and good timing. [(Source)](https://github.com/marcelocmachado/IMDb/blob/main/scrapingCode.md) 

Who are the most frequent actors in the Top 250 movies?

![Screenshot](/plots/plot_topActors.png)

> _**Robert De Niro**_ figures at the top of the list with **9** appearences. De Niro is famous for his roles in movies such as The Godfather: Part II, Goodfellas and Taxi Driver - all three are in the Top 250. Following De Niro, Harrison Ford (7), Tom Hanks (6), Morgan Freeman (6) and Leonardo DiCaprio (6) have significant number of appearences.

We already know the most popular Directors and Actors. But what are the **Average Ratings** of the movies they took part in?

### AVERAGE RATING FOR TOP DIRECTORS

The plot below shows the avarage rating for the most frequent directors among the Top 250 movies:

![Screenshot](/plots/plot_avgRatDirect.png)

> _**Chirstopher Nolan**_, famous for the Batman Trilogy and Inception, has the highest average rating for his movies: **8.53/10**. After Nolan, Steven Spielberg (8.34), Martin Scorsese (8.3), Stanley Kubrick (8.29) and Akira Kurosawa have pretty similar averages.

### AVERAGE RATING FOR TOP ACTORS

Regarding actors, let's see who has the highest average ratings:

![Screenshot](/plots/plot_avgRatActors.png)

> _**Morgan Freeman**_, pushed by the Top 1 and Top 4 movies (The Shawshank Redemption and Dark Knight, respectively) leads the top rated actors, with an average of **8.57/10**. Tom Hanks, known for his main role in Forrest Gump, follows at the second place with an average of **8.45/10**.

### AVG RATING BY DECADE

Next, we are going to analyze the decades with the highest average ratings:

![Screenshot](/plots/plot_avgRatDecade.png)

> From what we can see from the graph, the **1990's** have the highest average rating: **8.36/10**. Three of the Top 10 rated movies are from the 90's: The Shawshank Redemption, Schindler's List and Pulp Fition. At the second place, the 1970's have an average rating of 8.29/10, and with two movies in the Top 10 ratings: The Godfather and The Godfather: Part II.

### AVG RUNTIME BY DECADE

Do the decades in which the movies were released have an influence on the average duration of movies?

![Screenshot](/plots/plor_avgRunDecade.png)

> In the 1920's, movies clearly lasted for a shorter time. From 1930's onward, the runtime of movies appear to be consistent, with the highest average durations being in the 2020's (147.2 minutes) and 1960's (141.11 minutes), at least within the Top 250 rated movies.

### RUNTIME DENSITY

The next graph shows movies' duration density:

![Screenshot](/plots/plot_FreqRunTime.png)

### RATING DENSITY

Finally, the last plot shows movie's ratings density: 

![Screenshot](/plots/plot_FreqRatings.png)

