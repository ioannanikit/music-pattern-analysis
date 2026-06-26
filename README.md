# Spotify Music Pattern Analysis & Automated Playlist Generator 

An end-to-end Data Science project in Python that explores statistical correlations between audio features (such as energy, loudness, valence, and tempo) and utilizes Unsupervised Machine Learning to automatically categorize songs into distinct mood-based playlists.

---

## Key Insights & Exploratory Data Analysis (EDA)

Before training the clustering model, an extensive Exploratory Data Analysis was conducted to identify how musical characteristics interact:
* **Energy vs. Loudness (+0.76):** A strong positive non-linear correlation was discovered. As acoustic pressure increases (approaching 0 dB), the perceived energy of the track scales exponentially.
* **Energy vs. Acousticness (-0.73):** A powerful inverse correlation, successfully differentiating organic/acoustic arrangements from high-tempo electronic, rock, or pop genres.
* **Danceability vs. Valence (+0.48):** A moderate positive correlation indicating that rhythmic, highly danceable tracks frequently express happier or more positive emotional tones.

---

## Tech Stack & Libraries Used

* **Language:** Python
* **Data Manipulation:** Pandas, NumPy
* **Data Visualization:** Seaborn, Matplotlib
* **Machine Learning:** Scikit-Learn (`KMeans`, `StandardScaler`)

---

## Methodology & Machine Learning Pipeline

1. **Data Cleaning:** Handled missing values and isolated key numerical audio features (`danceability`, `energy`, `valence`, `tempo`).
2. **Feature Scaling:** Applied `StandardScaler` to normalize the data distributions, ensuring that features with higher absolute values (like Tempo in BPM) do not disproportionately bias the clustering distance metrics.
3. **Clustering Algorithm:** Implemented **K-Means Clustering** ($k=4$) to partition the high-dimensional musical space into 4 homogeneous cohorts.

---

## Generated Playlist Profiles (Results)

The K-Means model successfully engineered 4 distinct "musical personalities" based on the mathematical averages of each cluster:

| Cluster ID | Playlist Archetype | Danceability | Energy | Valence | Tempo (BPM) | Recommended Genres |
| :---: | :--- | :---: | :---: | :---: | :---: | :--- |
| **Cluster 0** |  **High-Energy / Gym** | 0.44 | 0.81 | 0.35 | 147.9 | Rock, Metal, Punk, Drum & Bass |
| **Cluster 1** |  **Party / Feel-Good Hits** | 0.68 | 0.74 | 0.76 | 123.2 | Pop, Electronic, Club Dance |
| **Cluster 2** |  **Chill / Study Session** | 0.36 | 0.26 | 0.22 | 103.4 | Acoustic, Indie Ballads, Ambient |
| **Cluster 3** |  **Late Night Grooves** | 0.64 | 0.57 | 0.39 | 107.5 | R&B, Hip-Hop, Smooth Funk |

---
