CREATE DATABASE spotify_db;
USE spotify_db;

CREATE TABLE spotify_tracks (
    track_id VARCHAR(255) PRIMARY KEY,
    track_name VARCHAR(255),
    artist_name VARCHAR(255),
    album_name VARCHAR(255),
    genre VARCHAR(100),
    popularity INT,
    danceability FLOAT,
    energy FLOAT,
    loudness FLOAT,
    speechiness FLOAT,
    acousticness FLOAT,
    instrumentalness FLOAT,
    liveness FLOAT,
    valence FLOAT,
    tempo FLOAT,
    duration_ms INT,
    release_year INT
);

-- Import Data (CSV format)
LOAD DATA INFILE '/path/to/spotify_data.csv'
INTO TABLE spotify_tracks
FIELDS TERMINATED BY ','
ENCLOSED BY '"'
LINES TERMINATED BY '\n'
IGNORE 1 ROWS;

-- Top 10 Most Popular Songs
SELECT track_name, artist_name, popularity 
FROM spotify_tracks 
ORDER BY popularity DESC 
LIMIT 10;

-- Most Common Genres
SELECT genre, COUNT(*) AS count 
FROM spotify_tracks 
GROUP BY genre 
ORDER BY count DESC 
LIMIT 10;

-- Popularity Trend Over Years
SELECT release_year, AVG(popularity) AS avg_popularity 
FROM spotify_tracks 
GROUP BY release_year 
ORDER BY release_year;
