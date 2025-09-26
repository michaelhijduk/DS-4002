# Project 1 - Classifying Music Genres by Lyrics

## Data Devils: Michael Hijduk (leader), Laura Espuna, Anthony Jiang

### Software & Platform

#### Platform Used
- Development was done primarily on **macOS (Sonoma 14.0)**.
- It should also run on **Windows 10/11** as long as **Python 3.11** and the required packages are installed.

#### Software Used
- **Programming Language:** Python 3.11  
- **Version Control:** Git & GitHub  
- **IDE (recommended):** VS Code or Jupyter Notebook  

#### Required Packages
The following Python packages are required to run the project:  
- `lyricsgenius` (for retrieving lyrics data via the Genius API)  
- `requests` (for making HTTP requests to the Last.fm API)    
- `pandas` (for dataset manipulation and storage)  
- `numpy` (for numerical computations)    
- `matplotlib` (for visualization)  
- `wordcloud` (for generating word clouds)  
- `scikit-learn` (for TF-IDF feature extraction, model training, and evaluation)

- To install, run the following code:
```
pip install lyricsgenius requests pandas numpy matplotlib wordcloud scikit-learn

```

#### External APIs
- This project uses two APIs to gather music data:
  - Genius API --> Provides song lyrics
  - Last.fm API --> Provides genre-tagged top tracks.
- Both require API keys to be stored as environment variables:
```
export GENIUS_API_KEY="your_genius_api_key"
export LASTFM_API_KEY="your_lastfm_api_key"
```


### Map of Repository
```
.
├── DATA
│   ├── README.md
│   ├── data.json
│   ├── sample_data.json
│   └── sample_data1.json
├── LICENSE
├── OUTPUT
│   ├── Number_of_songs_per_genre.png
│   ├── average_words_per_genre.png
│   ├── confusion_matrix.png
│   ├── probabilities_for_each_genre_for_specific_song.png
│   ├── some_predictions_based_on_lyrics.png
│   ├── top_10_words_country.png
│   ├── top_10_words_electronic.png
│   ├── top_10_words_hiphop.png
│   ├── top_10_words_jazz.png
│   ├── top_10_words_metal.png
│   ├── top_10_words_pop.png
│   ├── top_10_words_r&b.png
│   ├── top_10_words_rock.png
│   ├── training_and_test_scores.png
│   ├── word_cloud_country.png
│   ├── word_cloud_electronic.png
│   ├── word_cloud_hiphop.png
│   ├── word_cloud_jazz.png
│   ├── word_cloud_metal.png
│   ├── word_cloud_pop.png
│   ├── word_cloud_r&b.png
│   └── word_cloud_rock.png
├── README.md
├── REPORTS
│   └── MI1-Project1_Team7.pdf
└── SCRIPTS
    ├── data_cleaning.ipynb
    └── data_collection.ipynb

6 directories, 31 files

```
### Instructions for Reproduction

#### Step 0: Create Genius and Last.fm API keys to gather data (Optional: if you plan to collect your own data from the two APIs used in this project, otherwise skip to **Step 1**)
- Create the secret keys for each API
- Store them as environment variables on your local computer
- Make requests to the Last.fm API song titles and their artists from various genres of interest
- Use the Genius API to populate each song requested from the Last.fm API with their lyrics
- Make sure to save the data into a file to perform analysis

#### Step 1: Exploratory Data Analysis
- Organize the songs by genre (something like a dictionary where keys are song genres and values are a list of all songs in a specific genre)
- Count how many songs are in each genre (this should already be determined in the data collection step **(Step 0)**, but this is to confirm the number of songs from each genre is approximately the same to avoid bias)
- Clean the lyrics for each song (e.g., lowercasing, removing punctuation, removing linebreaks, etc.)
- Use the `wordcloud` library to generate word clouds for each genre to help visualize which words are most common in each genre
- Find the average number of words per song for each genre (by finding the sum of words in all lyrics for each genre and dividing the result by the number of songs in that genre)

#### Step 2: Set up for feature extraction and data training/testing
- Separate the data into two lists (list1 = [songOneLyrics, songTwoLyrics, ...], list2 = [songOneGenre, songTwoGenre, ...]) so that each song's lyrics in list1 matches its genre in list2
- Prep the Tf-idf vectorizer instance by setting parameters (e.g., lowercase=True, stop_words='english', ngram_range=(1, 2), max_features=5000)

#### Step 3: Training and Testing
- Split the dataset into an 80-20 split (80% for training and 20% for testing and make sure that the proportion of the genres in the training and test groups is roughly the same)
- Build data pipeline (vectorizer (Tf-idf) + classifier (logisticRegression))
- Using the pipeline, cross-validate (5-folds) on the training set
- Train the full training set
- Using the trained model, test it on the testing set

#### Step 4: Evaluate performance
- Print out the classification report of the model
- Construct confusion matrix to help visualize predicted labels vs true labels
- Print out some lyrics along with predicted labels and true labels
- Print out what words were quintessential for the model to predict a specific genre
- Look at the probabilities the trained model had for each genre for a specific song



