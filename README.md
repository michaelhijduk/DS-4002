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

