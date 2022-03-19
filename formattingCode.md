```r
# Removing the spaces in the strings to facilitate the string split for later
imdb$cast = gsub(", ",",",imdb$cast)
imdb$director = gsub(", ",",",imdb$director)
imdb$genre = gsub(", ",",",imdb$genre)

# Adjusting format: runtime was a character type. Using chron package to convert to time
imdb$runTime = chron(times = imdb$runTime)

# Turning into character again to extract hours and minutes (now it is in the right format with two digits for hours, minutes and seconds)
imdb$runTime = as.character(imdb$runTime)

# Extracting hours and minutes
imdb$hours = as.numeric(substr(imdb$runTime, 1, 2))
imdb$mins = as.numeric(substr(imdb$runTime, 4, 5))

# Runtime in minutes
imdb$totalRunTime = (imdb$hours*60)+imdb$mins

# Appending a column for the decade
imdb$decade = as.numeric(paste0(substr(as.character(imdb$year),1,3), 0))

# Correcting genres (some genres have a hyphen and that separates the string as two different genres)
imdb$genre = gsub("Sci-,Fi", "Sci-Fi", imdb$genre)
imdb$genre = gsub("Film-,Noir", "Film-Noir", imdb$genre)

# Compressed votes (column that shows the number of votes in a compressed format: 1.2M, 750K, etc)
comprss <- function(tx) { 
    div <- findInterval(tx, 
                        c(0, 1e3, 1e6, 1e9, 1e12) )  # modify this if negative numbers are possible
    paste(round(tx/10^(3*(div-1)), 2), 
          c("","K","M","B","T")[div] )}

imdb$votesComp = comprss(imdb$votes)
```
