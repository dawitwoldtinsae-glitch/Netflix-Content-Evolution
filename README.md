# Netflix Content Evolution

## Overview

This project explores how the **composition of titles added to Netflix changed over time**.

Rather than focusing only on how many titles were added, the analysis examines changes in the makeup of those additions across several dimensions: content type, genre, country, rating, and content characteristics.

The project follows an exploratory data analysis workflow:

**Research questions → Data understanding → Cleaning → Transformation → Analysis → Visualization → Interpretation**

---

## Research Question

> **How did Netflix's content composition change over time?**

To answer the broad question, the project is divided into six more specific questions:

1. **Content Type** — How did the balance between Movies and TV Shows change over time?
2. **Genre Composition** — How did the genre composition change over time?
3. **Geographic Composition** — How did the geographic composition change over time?
4. **Content Rating** — Did the distribution of content ratings change over time?
5. **Content Characteristics** — Did movie runtime and the number of TV Show seasons change over time?
6. **Content Diversity** — How did the overall composition of titles added to Netflix become more varied across these dimensions?

The sixth question is treated as a synthesis of the findings from the previous analyses rather than as a separate formal diversity metric.

---

## Dataset

The project uses the **Netflix Movies and TV Shows** dataset containing information about titles represented as being added to Netflix.

The original dataset contains **8,807 records and 12 columns**, including:

* `show_id`
* `type`
* `title`
* `director`
* `cast`
* `country`
* `date_added`
* `release_year`
* `rating`
* `duration`
* `listed_in`
* `description`

The main time variable is `date_added`, because the project examines how the composition of **titles added to Netflix** changed over time.

The cleaned dataset contains **8,797 records** after removing the 10 records with missing `date_added` values.

> **Important:** `release_year` represents when a title was originally released, while `date_added` represents when it was added to Netflix. These variables were kept separate throughout the analysis.

---

## Analysis

### 1. Content Type

The first analysis examines the proportion of Movies and TV Shows among titles added in each year.

The results show that Movies remained the larger component, while TV Shows became a substantial and recurring part of Netflix additions during the later years of the dataset.

[View the content type visualization](images/movies_vs_tv_shows.png)

---

### 2. Genre Composition

The genre analysis examines changes in the proportions of major genre assignments over time.

Because a title can belong to multiple genres, genre data was split and expanded so that each title-genre assignment could be analyzed. Ambiguous labels such as general `TV Shows` and `Movies` categories were excluded from the selected genre analysis.

The visualization focuses on the major genre categories and shows how their relative shares changed over time.

[View the genre visualization](images/Selected_Major_Genre.png)

---

### 3. Geographic Composition

The geographic analysis examines how the countries associated with titles changed over time.

Titles associated with multiple countries were expanded into separate title-country assignments. Each listed country receives one assignment rather than fractional weighting.

The United States remained the largest contributor in the dataset, while the relative share of other countries became more substantial during the later period.

[View the geographic visualization](images/selected_major_country.png)

---

### 4. Content Rating

Movies and TV Shows were analyzed separately because their rating distributions use different rating systems.

For Movies, the rating composition changed noticeably over time, with TV-MA becoming less dominant while ratings such as R and PG-13 became more prominent in the later period.

For TV Shows, TV-14 was the largest rating in 2016 and 2017, after which TV-MA became the dominant rating from 2018 onward.

[View the Movie rating visualization](images/Movies_By_Selected_Rating.png)

[View the TV Show rating visualization](images/TV_Shows_Rating.png)

---

### 5. Content Characteristics

Movies and TV Shows were analyzed separately because their `duration` values represent different characteristics:

* **Movies:** runtime in minutes
* **TV Shows:** number of seasons

#### Movie Runtime

The runtime distribution shifted toward longer ranges during the later period. Movies in the 90–119 minute and 120–149 minute ranges became more prominent, while shorter runtime ranges declined.

The mean and median runtime also increased from 2016 to 2021, providing a second perspective on the distributional change.

[View the mean and median movie runtime visualization](images/Mean_and_Median_Movie_Runtime.png)

#### TV Show Seasons

One-season TV Shows remained the largest category, but their share declined during the later period. At the same time, two-season and three-season shows became more common.

[View the TV Show duration visualization](images/TV%20Show%20Durations_bar.png)

---

## Key Findings

Overall, the analysis shows that the composition of titles added to Netflix was **not static** over the observed period.

### Content type

Movies remained the majority of additions, but TV Shows became a much more substantial component during the later period.

### Genre

The relative contribution of major genres changed over time rather than remaining constant.

### Geography

The United States remained dominant in country assignments, but its share declined during the later period as other countries accounted for a larger proportion of the geographic distribution.

### Ratings

Movie and TV Show rating distributions both changed over time, with different patterns between the two content types.

### Content characteristics

Movie runtimes shifted toward longer ranges, while TV Shows showed a shift away from the strong concentration in one-season shows toward a larger presence of multi-season shows.

Taken together, these findings indicate that the composition of titles added to Netflix changed across multiple dimensions rather than following a single simple trend.

---

## Visualizations

All major project visualizations are stored in the [`images/`](images/) folder.

| Visualization                                                             | Description                                                |
| ------------------------------------------------------------------------- | ---------------------------------------------------------- |
| [Movies vs TV Shows](images/movies_vs_tv_shows.png)                       | Proportion of Movies and TV Shows added by year            |
| [Selected Major Genres](images/Selected_Major_Genre.png)                  | Proportion of selected major genre assignments over time   |
| [Selected Major Countries](images/selected_major_country.png)             | Proportion of selected major country assignments over time |
| [Movies by Selected Rating](images/Movies_By_Selected_Rating.png)         | Movie rating composition over time                         |
| [TV Shows by Rating](images/TV_Shows_Rating.png)                          | TV Show rating composition over time                       |
| [Mean and Median Movie Runtime](images/Mean_and_Median_Movie_Runtime.png) | Mean and median movie runtime over time                    |
| [TV Show Durations](images/TV%20Show%20Durations_bar.png)                 | TV Show season-count composition over time                 |

---

## Repository Structure

```text
Netflix Content Evolution/
│
├── data/
│   ├── netflix_titles.csv
│   └── netflix_cleaned.csv
│
├── images/
│   ├── movies_vs_tv_shows.png
│   ├── Selected_Major_Genre.png
│   ├── selected_major_country.png
│   ├── Movies_By_Selected_Rating.png
│   ├── TV_Shows_Rating.png
│   ├── Mean_and_Median_Movie_Runtime.png
│   └── TV Show Durations_bar.png
│
├── notebooks/
│   ├── 01_data_understanding_and_cleaning.ipynb
│   ├── 02_content_type_analysis.ipynb
│   ├── 03_genre_analysis.ipynb
│   ├── 04_geographic_analysis.ipynb
│   ├── 05_rating_analysis.ipynb
│   └── 06_content_characteristics.ipynb
│
└── README.md
```

---

## Notebooks

Each notebook corresponds to a stage of the analysis:

**01 — Data Understanding and Cleaning**
Examines the dataset structure, missing values, duplicates, data types, and prepares the cleaned dataset.

**02 — Content Type Analysis**
Analyzes how the proportion of Movies and TV Shows changed over time.

**03 — Genre Analysis**
Examines changes in the composition of major genres.

**04 — Geographic Analysis**
Explores changes in the countries associated with titles added to Netflix.

**05 — Rating Analysis**
Analyzes Movie and TV Show rating distributions separately.

**06 — Content Characteristics**
Examines movie runtime and TV Show season-count distributions over time.

---

## Limitations

This project has several important limitations.

* The dataset does not represent every title ever added to Netflix. The conclusions apply to the titles represented in this dataset.
* Early years contain very few observations, making their yearly proportions unstable. Most substantive interpretations therefore focus on the later years where the number of observations is much larger.
* Titles can have multiple genres and countries, meaning genre and geographic analyses are based on assignments rather than unique-title counts.
* Rating labels are retained as recorded in the dataset and analyzed separately for Movies and TV Shows.
* The project describes changes in composition; it does not establish that Netflix intentionally adopted a particular content strategy.
* The diversity conclusion is descriptive rather than a formal numerical diversity measurement.

---

## Tools Used

* Python
* Pandas
* NumPy
* Matplotlib
* Jupyter Notebook

---

## Conclusion

This project demonstrates how exploratory data analysis can be used to investigate how a dataset's composition changes over time.

Across content type, genre, geography, rating, and content characteristics, the data shows meaningful changes in the titles represented as being added to Netflix. Rather than relying on a single metric, the project combines multiple perspectives to build a more complete picture of how the composition of these additions evolved over the observed period.
