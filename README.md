# Game of Thrones Data Analysis

## Overview
This project analyzes data from the popular TV series *Game of Thrones*. Using Python libraries such as Pandas, Matplotlib, and Seaborn, it explores trends in episode ratings, viewership, and season-wise episode distribution.

## Questions Answered
- How many episodes are there per season?
- How does viewership trend across seasons?
- Which episode has the highest IMDb rating?
- Which episode has the lowest IMDb rating?
- Who are the top 5 directors with the most episodes?
- Who are the top 5 writers with the most episodes?
- Who are the top 5 cinematographers?
- Who are the top 5 editors?
- What are the seasonal trends in IMDb ratings?
- What are the seasonal trends in Rotten Tomatoes ratings?
- What are the seasonal trends in Metacritic ratings?
- Which novel is most frequently used in *Game of Thrones*?
- How do novel adaptations trend in the series?

## Features
- Loads and processes a CSV file containing Game of Thrones episode data.
- Drops unnecessary columns to clean the dataset.
- Analyzes the number of episodes per season.
- Visualizes viewership trends across seasons using Seaborn.
- Identifies the highest and lowest-rated episodes based on IMDb ratings.
- Determines the most frequent directors, writers, cinematographers, and editors.
- Analyzes seasonal rating trends across multiple review platforms.
- Explores the influence of novels on the TV series.

## Requirements
To run this project, ensure you have the following dependencies installed:

```bash
pip install pandas matplotlib seaborn
```

## Usage
1. Load the dataset:
    ```python
    import pandas as pd
    df = pd.read_csv("Game_of_Thrones.csv")
    ```
2. Clean the dataset:
    ```python
    df = df.drop(['Original Air Date', 'Filming Duration', 'Ordered', 'Synopsis'], axis=1)
    ```
3. Analyze episode count per season:
    ```python
    season_ep_count = df.groupby('Season').size()
    print(season_ep_count)
    ```
4. Visualize viewership trends:
    ```python
    import matplotlib.pyplot as plt
    import seaborn as sns
    
    sns.lineplot(x=df['Season'], y=df['U.S. Viewers (Millions)'])
    plt.title("Viewership Over Seasons")
    plt.xlabel('Season')
    plt.ylabel('U.S. Viewership (Millions)')
    plt.show()
    ```
5. Identify highest and lowest-rated episodes:
    ```python
    top_rated = df.loc[df['IMDb Rating'].idxmax()]
    lowest_rated = df.loc[df['IMDb Rating'].idxmin()]
    print("Highest rated episode:\n", top_rated[['Title of the Episode', 'IMDb Rating']])
    print("Lowest rated episode:\n", lowest_rated[['Title of the Episode', 'IMDb Rating']])
    ```

## Conclusion
This analysis provides insights into *Game of Thrones* viewership patterns and episode ratings. You can extend it further by exploring correlations between ratings and other factors, such as runtime or writer/director influence.

