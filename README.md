# 🎵 Spotify Data Analysis and Query Optimization

![Image](https://github.com/user-attachments/assets/a392c2db-9b38-4186-b235-1c4e4937e069)

## 📌 Project Overview

Welcome to the Spotify SQL Data Analysis Project, where we explore music trends, artist insights, and track statistics using SQL. This project involves writing and optimizing 18 SQL queries to uncover patterns in streaming data, track performance, and listener engagement.

## 📂 Dataset Details

#### The dataset consists of various attributes related to tracks, albums, and artists, helping us analyze song performance and popularity.

🎤 **Artist:** Name of the performer

🎵 **Track:** Name of the song

💽 **Album:** Album name and type (Single/Album)

🎚️ **Audio Features:** Danceability, Energy, Tempo, Loudness

📈 **Popularity Metrics:** Views, Likes, Comments, Streams

🎶 **Audio Analysis:** Liveness, Acousticness, Speechiness

```sql
-- create table
DROP TABLE IF EXISTS spotify;
CREATE TABLE spotify (
    artist VARCHAR(255),
    track VARCHAR(255),
    album VARCHAR(255),
    album_type VARCHAR(50),
    danceability FLOAT,
    energy FLOAT,
    loudness FLOAT,
    speechiness FLOAT,
    acousticness FLOAT,
    instrumentalness FLOAT,
    liveness FLOAT,
    valence FLOAT,
    tempo FLOAT,
    duration_min FLOAT,
    title VARCHAR(255),
    channel VARCHAR(255),
    views FLOAT,
    likes BIGINT,
    comments BIGINT,
    licensed BOOLEAN,
    official_video BOOLEAN,
    stream BIGINT,
    energy_liveness FLOAT,
    most_played_on VARCHAR(50)
);
```

## 🔍 Query Categories & Insights

### 🎯 Basic Queries (Easy Level)

*  Retrieve tracks with more than 1 billion streams.
* List all albums with their respective artists.
*  Get the total comments for licensed tracks.
*  Find all tracks categorized under single albums.
*  Count the total number of tracks by each artist.

### ⚡ Analytical Queries (Intermediate Level)

* Calculate the average danceability of tracks per album.
* Identify the top 5 tracks with the highest energy levels.
* List tracks with their views & likes for official music videos.
* Compute the total views per album.  
* Compare Spotify vs. YouTube streams for tracks.
* Find the percentage of official music videos vs. non-official uploads.
* Identify the fastest-growing song based on streams per like ratio.

### 🚀 Advanced SQL Techniques (Advanced Level)

* Retrieve the top 3 most-viewed tracks for each artist using window functions.
* Find tracks where the liveness score exceeds the average.
* Use Common Table Expressions (CTEs) to calculate energy range per album.  
* Extract tracks where the energy-to-liveness ratio exceeds 1.2.
* Compute the cumulative sum of likes, ordered by track popularity.
* Predict the next trending song based on high energy, high danceability, and low views.

## 📊 Key Insights

🔹 Tracks with over 1 billion streams are dominated by globally popular artists.  
🔹 Album-based analysis shows that single albums have a higher average energy level than full-length albums.  
🔹 Songs with high danceability and energy tend to have higher engagement and future trending potential.  
🔹 Official music videos make up approximately X% of all video-based track content.  
🔹 Fastest-growing songs are identified by a strong ratio of streams per like, indicating viral trends.  
🔹 Energy-to-liveness ratio helps in identifying tracks suited for live performances.  
🔹 The top 3 most-viewed tracks per artist showcase diverse fanbase interests across different regions.

## ⚡ Query Optimization Techniques

- 🛠 Enabling Execution Plans in MS SQL Server

- To analyze query performance, execution plans were enabled in SQL Server Management Studio (SSMS) using:

- 🎯 **CTRL + M** to enable the Actual Execution Plan

- 🎯 **CTRL + L** for the Estimated Execution Plan

- 🎯 SET **SHOWPLAN_ALL ON** ; or SET **SHOWPLAN_XML ON** ; to analyze without execution

### 🚀 Optimization Strategies

🔹 1. Analyzing Query Performance

Used SET STATISTICS TIME, IO ON; to measure execution time and I/O cost.

Example before optimization:

```sql
SELECT 
	Artist, Track, Views_by
FROM spotify
WHERE Artist = 'Gorillaz' and most_playedon = 'Youtube'
ORDER BY Stream DESC;
```

⚡ Execution time before indexing

![Image](https://github.com/user-attachments/assets/6bf88ef5-924f-43a1-8245-555c470d0f65)


🔹 2. Indexing for Faster Retrieval

Created an index on frequently searched columns to improve speed:
```sql
CREATE INDEX Artist_index ON spotify (Artist);
```
⚡ Execution time after indexing: 

![Image](https://github.com/user-attachments/assets/24c0427d-2291-461a-8935-b58455d0b782)


🔹 3. Optimizing Query Structures

Avoided SELECT * and used only required columns.

Used JOINs efficiently instead of correlated subqueries.

Applied Partitioning and Filtering to reduce dataset scope.

🔹 4. Using Proper Data Types & Normalization

Ensured indexed columns used appropriate data types for efficiency.

Applied Normalization to reduce data redundancy and improve query speed.

🔹 5. Performance Gains (Before vs. After Optimization)

⏳ Execution time reduced by 90%

💾 I/O cost minimized significantly

📉 Query complexity reduced, leading to improved efficiency

### 🏗️ Technology Stack

**Database:** Microsoft SQL Server

**SQL Techniques:** Joins, Aggregations, Window Functions, Indexing, Query Optimization

**Tools Used:** SSMS (SQL Server Management Studio)

## 🔗 SQL File

**The SQL queries used for analysis are provided separately in the project repository. Please refer to the SQL file for detailed query execution.**











