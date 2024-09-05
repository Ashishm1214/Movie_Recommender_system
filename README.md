Dataset Link - https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata

## Movie Recommendation System

### Overview
This project involves creating a movie recommendation system using a dataset containing movie attributes. The goal is to recommend movies similar to a given movie based on content similarity.

### Dataset
The dataset includes the following columns: `budget`, `genres`, `homepage`, `id`, `keywords`, `original_language`, `original_title`, `overview`, `popularity`, `production_companies`, `runtime`, `spoken_languages`, `status`, `tagline`, `title`, `vote_average`, and `vote_count`.

### Data Preprocessing
1. **Handling Missing Values**: Missing values were identified and handled. Specifically:
   - `overview` had 3 missing values, which were removed.
   - Other columns had no missing values.
   - No duplicate entries were found in the dataset.

2. **Data Transformation**:
   - **Genres, Keywords, Cast, and Crew**: Extracted and converted relevant information to a list format.
   - **Tags Creation**: Combined `overview`, `genres`, `keywords`, `cast`, and `crew` into a single `tags` column for each movie.
   - **Text Normalization**: Applied stemming to the `tags` column using the Porter Stemmer to standardize the text data.

### Feature Extraction
- **Count Vectorization**: Converted the `tags` into numerical features using `CountVectorizer` with a maximum of 5000 features and excluding common stop words.

### Similarity Measurement
- **Cosine Similarity**: Calculated pairwise cosine similarity between movies based on their vectorized tags to quantify content similarity.

### Recommendation System
- **Functionality**:
  - The `recommend` function finds the most similar movies to a given movie based on cosine similarity scores.
  - It excludes the movie itself and returns the top 5 most similar movies.

### Example
For the movie "Avatar", the system recommended:
- "Titan A.E."
- "Small Soldiers"
- "Independence Day"
- "Ender's Game"
- "Aliens vs Predator: Requiem"

### Conclusion
This recommendation system effectively suggests movies similar in content to the input movie, enhancing user experience by providing relevant suggestions based on textual analysis.
