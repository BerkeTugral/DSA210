# DSA 210 Project: Video Game Sales vs. Speedrunning Popularity

## Project Idea
For my DSA 210 term project, I want to analyse the market of video games and speedrunning to figure out something not observed before: do popular games (the ones that sell alot of copies) get speedrun attempts more, or is it the niche games that have the right kind of design that speedrunners love? Speedrunning is this thrilling part of gaming where players try to beat games as fast as they can, often finding glitches or tricks to shave off seconds. I think it’ll be fun to see if big sellers like "Call of Duty" or "Minecraft" have a lot of speedrunning action, or if it’s more obscure titles like "Celeste" that get the speedrunning crowd excited. This project is a mix of my love for gaming and my curiosity about what makes certain games stick with players in unique ways.

## Motivation
I’ve always been into video games, and  I love watching speedrunning attempts where players blend their ingenuity and the limits of video games like in attempts to speedrun "The Elder Scrolls V Skyrim". It got me thinking about why some games become speedrunning classics while others don’t, Especially since Skyrim had years to be developed and hundreds of millions in budgeting yet games like Celeste didn't even have one percent of the budget. Sales numbers show how popular a game is with the general public, but speedrunning feels like a different kind of popularity—one that’s about replayability and community. I’m motivated to explore this because it’s a fun way to combine data science with something I enjoy, and I think it could reveal some neat patterns about game design and player engagement.

## Data Source
I’ll be working with two datasets for this project:
1. **Video Game Sales Dataset**
   - **Where I’m Getting It**: Kaggle (https://www.kaggle.com/datasets/gregorut/videogamesales)
   - **What It Has**: This dataset includes over 16,000 games with info like game names, platforms (e.g., PS4, Nintendo 64), release years, genres, publishers, and sales figures for different regions (North America, Europe, Japan, and Global). It covers games from 1980 to 2016.
   - **How I’ll Collect It**: I’ll download the `vgsales.csv` file from Kaggle. I’ve already checked, and it’s available with a free Kaggle account. It’s a simple CSV file, so I’ll use Python’s `pandas` to load and clean it.

2. **Speedrunning Data**
   - **Where I’m Getting It**: Speedrun.com API (https://github.com/speedruncomorg/api)
   - **What It Has**: This API gives data on speedrunning for tons of games, including world record times, the number of runs submitted, the number of players, and different categories (like Any% or 100%). It’s current data, so it reflects speedrunning activity up to 2025.
   - **How I’ll Collect It**: I’ll use Python to make requests to the Speedrun.com API. It’s a public API with no key needed.

## Plans for Data Collection
Here’s how I plan to get and prepare the data:
- **Kaggle Dataset**: I’ll download the `vgsales.csv` file from Kaggle and load it into Python with `pandas`. Since it has over 16,000 games, I’ll pick a smaller group—maybe the top 100 or 200 by global sales , and I shall focus on genres like platformers or RPGs that are popular with speedrunners. I’ll clean up the data, like fixing missing values or standardizing names, to make it easier to match with the speedrunning data.
- **Speedrunning Data**: I’ll write a Python script using the `requests` library to pull data from the Speedrun.com API. I’ll start by searching for each game in my subset by name and platform (e.g., "Super Mario 64" on Nintendo 64), then get the run data for popular categories like Any%. The API has a limit of 100 requests per minute, so I’ll add delays (like `time.sleep(1)`) to stay under that. I’ll save the data in a CSV file or a `pandas` DataFrame.
- **Merging the Data**: I’ll combine the two datasets by matching game names and platforms. Since names might not match perfectly (e.g., "Super Mario" vs. "Mario"), I’ll use a Python library like `fuzzywuzzy` to do fuzzy matching. I’ll end up with a dataset that has sales figures and speedrunning metrics for each game in my subset.
- **Timeline**: I’ll finish collecting and merging the data by April 18, 2025, as the project guidelines say that’s when exploratory analysis is due.

## Next Steps
After I get the data ready, here’s what I’ll do:
- **Exploratory Data Analysis (EDA)**: By April 18, 2025, I’ll look at sales trends (like which genres or platforms sell the most) and speedrunning trends (like which games have the most runs or players). I’ll make some charts with Python libraries like `matplotlib` or `seaborn` to see the patterns.
- **Machine Learning**: By May 23, 2025, I’ll try some ML stuff, like regression to see if sales predict speedrunning activity, or clustering to group games by sales and speedrunning popularity. This will help me answer my main question about popular vs. niche games.
- **Final Submission**: By May 30, 2025, I’ll wrap it up with a report that shows my findings, visualizations, and conclusions.

## Technical Details
- **Code**: I’ll write everything in Python. I’ll use libraries like `pandas` for data handling, `requests` for the API, `fuzzywuzzy` for matching, and `scikit-learn` for ML.
- 
- **GitHub**: I’ll put all my code and files in this GitHub repo and commit regularly so my progress is tracked. I’ll include a `requirements.txt` file with all the Python libraries I use, like `pandas`, `requests`, and `scikit-learn`.
- **Reproducibility**: In the final `README.md`, I’ll add instructions on how to run my code, including how to download the Kaggle dataset and use the Speedrun.com API.

## Academic Integrity
I’ll make sure to cite all my sources properly. The Kaggle dataset comes from Gregory Smith (the uploader), and the Speedrun.com API is from their public documentation. I used Grok to help me find the relevant datasets from Kaggle and the API for speedrunning Data API. Also I asked Grok to learn about how to pull the datas and which libraries to use in python because as of now I don't have much experience in utilizing a diverse set of python libraries to achieve such a goal. For example, I asked Grok, “Help me confirm access to the Kaggle Video Game Sales dataset and Speedrun.com API data, and give me suggestions about the relevant python methods to utilize them.” and it gave me useful info that I’ve rewritten in my own words here. Any code or ideas I get from elsewhere (like Stack Overflow or tutorials) will be credited too.

## Why This Works
I’ve checked that both datasets are accessible. The Kaggle dataset is a simple download, and the Speedrun.com API is a tested and true API which is used commonly in the" speedrun community. The Kaggle data ends in 2016, but lots of those games, like "Super Mario 64" and "The Legend of Zelda: Ocarina of Time," are still big in speedrunning, so I think it’ll work fine. If I run into issues with newer games not being in the Kaggle dataset, I might look for a small update later, but for now, I’ll stick with the current datasets.

This project is planned to give answers for developers to enrich gameplay experience by making their games speedrunnable and if there is a direct correlation between video game sales (it is assumed that more sales mean bigger the studio, the more extended the dev time and budgeting for an individual game, therefore a larger game to play implying more potential for speedrunning.) , which I'd love to look into because both it is something I enjoy spending my spare time watching speedrunners and also this might potentially be a valuable exercise to determine an aspect of a game I'd like to work on in the future.
