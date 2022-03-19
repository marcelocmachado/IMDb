```r
#### IMDb Top 250 Movies Web Scraping ####

# Loading packages
library('rvest')
library('dplyr')
library('tidyverse')
library("writexl")
library('readxl')

# Web Scraping

# Link for the Top 250 Movies
link = "https://www.imdb.com/chart/top/?ref_=nv_mv_250"
page = read_html(link)

# Assigning variables for movie name, year and rating
name = page %>% html_nodes(".titleColumn a") %>% html_text()
year = page %>% html_nodes(".secondaryInfo") %>% html_text()
year = as.numeric(gsub("[()]", "", year)) # cleaning the year
rating = page %>% html_nodes("strong") %>% html_text()
rating = as.numeric(rating)

# Getting the reference code for each movie
href = gsub("\\?.*","",page %>% html_nodes(".titleColumn a")) # remove after this
href = gsub('^.*\\"',"", href) # remove before this

# Link to movies to get specific info about each one - gets the main link and adds the movie code
movieLinks = href %>% paste("https://www.imdb.com", ., sep="")

# CAST
# Creating function to scrape all 10 first actors
castLinks = "fullcredits/?ref_=tt_ql_cl" %>% paste(movieLinks, ., sep="")

getCast = function(castLink) {
    castPage = read_html(castLink) 
    fullCast = castPage %>% html_nodes(".primary_photo+ td a") %>% html_text()
    fullCast = gsub("\n", "", fullCast)
    fullCast = fullCast[1:10]
    fullCast = fullCast %>% paste(collapse = ", ")
    return(fullCast)
}

# Applying function to every movie link
cast = sapply(castLinks, getCast, USE.NAMES = FALSE)

# DIRECTOR
# Creating function to scrape all directors
getDirector = function(dirLink) {
    dirPage = read_html(dirLink)
    dir = dirPage %>% html_nodes("#director+ .simpleCreditsTable a") %>% html_text()
    dir = gsub("\n", "", dir)
    dir = dir %>% paste(collapse = ", ")
    return(dir)
}

# Applying function to every movie link
director = sapply(castLinks, getDirector, USE.NAMES = FALSE)

# VOTES
# Votes are accessible through a secondary page. Creating an additional string and pasting to the movie links to access votes
voteLinks = "ratings/?ref_=tt_ov_rt" %>% paste(movieLinks, ., sep="")

# Creating function to scrape how many votes each movie received
getVote = function(voteLink) {
    votePage = read_html(voteLink)
    allVotes = votePage %>% html_nodes("div.smallcell") %>% html_text()
    allVotes = gsub("\n","", allVotes)
    allVotes = gsub(" ","", allVotes)
    allVotes = as.numeric(gsub(",", "", allVotes))
    allVotes = allVotes[1]
    return(allVotes)
}

# Applying function to every movie link
votes = sapply(voteLinks, getVote, USE.NAMES = FALSE)

# GENRE
# Creating function to scrape each movie's genres
getGenre = function(genreLink) {
    genrePage = read_html(genreLink)
    genres = genrePage %>% html_nodes('li.ipc-metadata-list__item') %>% html_text()
    genres = subset(genres, grepl("Genre", genres))
    genres = gsub("Genres","", genres)
    genres = gsub("Genre","", genres)
    genres = gsub('(([[:upper:]]))', ', \\1', genres)
    genres = substring(genres, 3)
    return(genres)
}

# Applying function to every movie link
genre = sapply(movieLinks, getGenre, USE.NAMES = FALSE)
genre = unlist(genre)

# RUN TIME
# Creating function to scrape each movie's running time
    timePage = read_html(timeLink)
    time = timePage %>% html_nodes("div.sc-f65f65be-0.ktSkVi") %>% html_text()
    time = subset(time, grepl("Runtime", time))
    time = gsub("(min).*","\\1",time)
    time = gsub("Color.*","\\1",time)
    time = gsub("Runtime", "", time)
    time = gsub("s", "", time)
    time = gsub(" hour", ":", time)
    time = ifelse(grepl("min", time, fixed = FALSE), paste0(gsub(" min", "", time), ":00"), paste0(time, ":00:00"))
    time = gsub(" ", "", time)
    time = ifelse(nchar(time) < 6, paste0("00:", time), paste0(time, ""))
    time = gsub("::", ":", time)
    return(time)
}

# Applying function to every movie link
runTime = sapply(movieLinks, getTime, USE.NAMES = FALSE)

# Final data frame
movies = data.frame(name, year, rating, cast, director, genre, votes, runTime)

```
