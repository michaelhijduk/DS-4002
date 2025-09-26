# Project Data Metadata

## 1. Data Summary
This folder contains all datasets used and generated in this project:
The dataset includes 2000 songs across 8 music genres (pop, rock, electronic, country, metal, hip-hop, jazz, and
R&B). The dataset contains the top 250 songs from each genre from the year 2025 to ensure that the data is
uniform and bias can be minimized in the model training. The following features are collected from each song:
title, artist, genre, and lyrics. The dataset is stored as a JSON file on GitHub, which makes it publicly accessible
through the repository’s file system. Anyone with the link to the file can view it directly in their browser or
download it by clicking the “Download raw file” button or using the raw file URL. This allows easy access for
analysis in Python (ex. Using json.load), R, or other tools that can read JSON.

## 2. Provenance
The dataset was created by programmatically gathering music data from two public APIs: Last.fm and Genius.
Using the Last.fm API, the top 250 tracks were retrieved for each of the eight genres, resulting in a diverse pool
of songs. For each track, metadata such as title, artist, and genre were stored in a JSON structure. Then, the
Genius API was used to query the corresponding lyrics by song title and artist, with preprocessing steps to remove section headers and handle retries for failed requests. Each track entry was enriched with lyrics when available, or left blank if lyrics could not be retrieved. This process produced a curated dataset that combines
structured metadata from Last.fm with lyrical content from Genius, allowing for exploratory analysis of music
across genres.


## 3. License
All original code in this project is released under the MIT license, allowing individuals to freely use, modify, and
distribute it with proper attribution. The dataset metadata was collected from Last.fm API may be used and
shared under the Last.fm API Terms of Service, which require proper attribution. However, the song lyrics
retrieved via the Genius API are copyrighted by the respective music publishers and are not covered by the MIT
license. While the repository contains lyrics for analysis purposes, redistribution of these lyrics without
permission would violate copyright law and Genius’ API terms. Users of this repository may use the lyrics locally
for personal analysis but must not publicly redistribute them. In summary, the MIT license applies only to the
code and any sharable metadata, while the lyrics remain protected intellectual property outside the scope of this
license.


## 4. Ethical Statements
The song lyrics included in this dataset are copyrighted material owned by their respective artists, songwriters,
and music labels. They are provided here solely for educational, research, or non-commercial purposes, such as
text analysis or natural language processing projects. Users must comply with the Terms of Service of the data
sources, such as the Genius API, and should not redistribute lyrics for commercial purposes. Proper attribution
to the original artists and sources is expected when using this dataset. Any usage beyond academic or research
contexts may require additional permissions from copyright holders.

## 5. Data Dictionary
| Column Name | Description | Potential Response |
|------------|-------------|------------------|
| name       | Title of the song | Expresso |
| artist     | Individual who performs/sings the original song | Sabrina Carpenter |
| genre      | Musical genre or style of the song (pop, rock, electronic, country, metal, hip hop, jazz, and R&B) | pop |
| lyrics     | The words/context of the song | "Now he's thinkin' 'bout me every night, oh<br>Is it that sweet? I guess so<br>Say you can't sleep, baby, I know<br>That's that me espresso<br>Move it up, down, left, right, oh<br>Switch it up like Nintendo<br>Say you can't sleep, baby, I know<br>That's that me espresso..." |

## 6. Explanatory Plots
- **Plot 1:** Distribution of `songs` by `genre`  
  ![Song Distribution](/OUTPUT/Number_of_songs_per_genre.png)
- **Plot 2:** Time series of `value`  
  ![Time Series](plots/value_timeseries.png)

