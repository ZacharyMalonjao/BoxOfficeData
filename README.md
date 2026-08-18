# Movie Box Office Insights

An exploratory data analysis and Tableau dashboard examining **5,000 movies released between 2000 and 2024** to understand what drives box-office performance, where movies are produced and consumed, and how audience behavior has changed over time.

The project combines **Python data cleaning and preparation** with **Tableau data visualization** to turn raw box-office data into an interactive story about movie performance, audience engagement, and the global film industry.

## Key Findings

* **Action and Animation** were the highest-grossing genres in the dataset, generating approximately **$3.68B** and **$3.61B** respectively.
* **International audiences generated 61.16% of total gross**, compared with 38.84% from the domestic/US market.
* The **United States was the dominant single-country producer**, while English was the most common production language.
* Box-office performance and audience engagement experienced a **sharp decline in 2020**, corresponding with the disruption caused by the COVID-19 pandemic.
* The industry showed a meaningful recovery after 2020, but **2024 had not fully returned to the pre-pandemic trajectory**.
* Recent high-performing films were heavily represented by **animation and established franchises**, including *Despicable Me 4*, *Moana 2*, *Wicked*, and *Kung Fu Panda 4*.
* High production volume and box-office performance did not necessarily correspond to the highest audience ratings, highlighting a distinction between **commercial success and critical/audience reception**.

## Dashboard

The final Tableau dashboard presents the analysis through several interactive views covering:

* Overall box-office performance
* Genre performance
* Domestic vs. foreign revenue
* Movie production by country
* Production language
* Audience ratings
* Reviewer engagement
* Changes in the box office over time

**Tableau Public:**
[View the interactive dashboard](https://public.tableau.com/app/profile/david.zachary.malonjao/viz/BoxOfficeData2000-2024/Intro?publish=yes)

> **Dashboard:** Box Office Data 2000–2024

## Project Questions

The analysis was organized around three questions:

### 1. Do people still watch movies?

How has movie consumption and box-office performance changed from 2000 to 2024?

### 2. Where are movies created and consumed?

Which countries and languages dominate film production, and where does box-office revenue come from?

### 3. What makes a film successful?

Which genres, markets, and characteristics are associated with stronger box-office performance?

---

# Data

### Dataset

**Movies Box Office Dataset (2000–2024)**

* **Records:** 5,000 movies
* **Years:** 2000–2024
* **Genres:** 18
* **Worldwide Gross:** $534.11B
* **Reviewer/Vote Count:** 11.61M

**Source:** Kaggle — Movies Box Office Dataset (2000–2024)

[Kaggle dataset](YOUR_KAGGLE_LINK)

The dataset contains information including movie release year, genre, production country, original language, domestic and foreign gross, worldwide gross, audience ratings, reviewer counts, and ranking.

---

# Data Preparation

The raw dataset required cleaning and standardization before it could be used for analysis.

Python and Pandas were used to prepare the data for Tableau.

### Data Quality Checks

The cleaning process included:

* Checking for duplicate records
* Identifying missing values
* Validating year ranges
* Converting numeric fields into appropriate data types
* Identifying invalid and extreme values
* Standardizing categorical values
* Normalizing text formatting
* Converting abbreviated language codes into readable language names

### Numeric Data

Continuous variables such as:

* Worldwide Gross
* Domestic Gross
* Domestic %
* Foreign Gross
* Foreign %

were converted to numeric values and checked for invalid values and extreme observations.

Missing or invalid observations were handled using **mean imputation**, with the upper 1% of observations treated as extreme values for the relevant continuous variables.

### Ratings

Movie ratings required additional processing because the original values contained formatting such as `8.2/10`.

A regular expression was used to extract the numeric rating before validating the resulting values against the expected **0–10 rating range**.

### Categorical Data

Genre and production-country fields contained multiple values within individual records. The first listed genre/country was retained as the primary category for analysis.

Text fields were also standardized by:

* Removing unnecessary whitespace
* Normalizing Unicode characters
* Standardizing formatting

Missing genre and production-country values were filled using the **mode** of the respective field.

### Production Language

Original language values were provided as abbreviated codes such as `en`, `ja`, `fr`, and `ko`.

These were mapped to their full language names, such as:

* `en` → English
* `ja` → Japanese
* `fr` → French
* `ko` → Korean

Missing language values were handled using mode imputation.

The resulting cleaned dataset was exported as:

`clean_box_office_data.csv`

---

# Analysis & Visualization

The cleaned dataset was imported into Tableau to create an interactive data story.

### Box Office Trends

Line charts were used to examine changes in domestic, foreign, and worldwide box-office performance over time.

This revealed a relatively steady growth period from 2000–2019, followed by a sharp decline in 2020 and an uneven recovery afterward.

### Genre Performance

Bar charts were used to compare box-office performance across genres.

**Action and Animation** emerged as the strongest-grossing genres in the dataset, followed by Drama, Horror, and Comedy.

### Geographic Distribution

A geographic visualization was used to show the countries represented in the dataset.

The analysis showed that movie production is heavily concentrated in the United States, with additional production clusters across East Asia, Europe, and South America.

### Domestic vs. Foreign Revenue

The dashboard compares domestic and foreign box-office revenue.

Despite the United States being the dominant production country, **61.16% of total gross came from foreign markets**, demonstrating the importance of international audiences to commercial movie performance.

### Language

A treemap was used to compare movies by original production language.

English was substantially more prevalent than other languages, followed by Japanese, French, and Korean.

### Ratings and Commercial Success

Scatter plots were used to examine the relationship between movie ratings and box-office performance.

The analysis suggests that commercial success does not automatically correspond to the highest ratings. High-revenue films can occupy a broad range of audience-rating levels.

---

# Key Insights

## 1. Movie Success

Recent high-grossing movies were strongly represented by animation and established franchises. Films such as *Despicable Me 4*, *Moana 2*, *Wicked*, and *Kung Fu Panda 4* demonstrate the continued commercial strength of recognizable intellectual properties and family-oriented releases.

Across the full dataset, Action and Animation generated the highest total gross.

This suggests that **large-scale spectacle, established franchises, and broadly accessible genres have significant commercial appeal**, although the analysis does not establish that genre alone causes a movie to succeed.

## 2. The Global Box Office

The United States is the dominant production country in the dataset, and English is the most common production language.

However, the majority of revenue comes from outside the domestic US market:

**Foreign: 61.16%**
**Domestic: 38.84%**

This highlights the importance of international audiences to the commercial performance of major films.

## 3. The Pandemic Disrupted Movie Consumption

Box-office performance and reviewer activity increased fairly steadily between 2000 and 2019 before experiencing a dramatic decline in 2020.

Both domestic and foreign revenue fell sharply, while reviewer counts also dropped.

The industry subsequently recovered, but the data through 2024 suggests that the box office had **not completely returned to its previous trajectory**.

## 4. Commercial Success vs. Ratings

The analysis also revealed that the films generating the most revenue were not necessarily the films receiving the highest ratings.

This is an important distinction when evaluating movie performance:

**Commercial success ≠ audience rating**

A film can achieve substantial box-office revenue because of factors such as franchise recognition, genre appeal, marketing, or international reach without necessarily receiving the highest ratings.

---

# Recommendations

Based on the patterns observed in the dataset, several considerations emerge for the film industry:

### Consider Global Audiences

Since foreign markets account for the majority of box-office revenue, international audiences are an important consideration for commercially ambitious releases.

Localization, subtitles, dubbing, and international marketing can help films reach audiences beyond their domestic market.

### Understand Established Demand

Action, Animation, Drama, Horror, and Comedy showed strong commercial performance within the dataset.

Established genres and recognizable franchises appear frequently among successful releases, suggesting that audience familiarity can be an important commercial consideration.

### Don't Equate Revenue With Quality

High box-office performance should not be treated as a direct measure of audience rating or overall quality.

Studios and analysts should consider both **commercial metrics and audience reception** when evaluating a film's performance.

---

# Tools & Technologies

* **Python**
* **Pandas**
* **Google Colab**
* **Tableau**
* **GitHub**
* **Kaggle Dataset**

### Workflow

`Raw Dataset → Python/Pandas Cleaning → Clean Dataset → Tableau → Interactive Dashboard → Insights`

---

# Project Structure

## File Structure

```
BoxOfficeData/
├── datasets/                     # cleaned box office data file
├── BoxOfficeDataCleaning.ipynb   # Data cleaning notebook (Colab)
└── README.md                     # Project overview and documentation
```


*Project structure may vary depending on the final repository organization.*

---

# Conclusion

This project explored 25 years of movie box-office data to understand how **genre, geography, language, audience engagement, and time** relate to commercial movie performance.

The analysis found that the global box office is heavily influenced by international audiences, with foreign markets generating the majority of revenue. Action and Animation were the strongest-grossing genres, while the COVID-19 pandemic created a significant disruption to the industry's growth trajectory.

More broadly, the project demonstrates how **data cleaning, exploratory analysis, visualization, and storytelling can be combined to turn a large dataset into actionable insights**.

The final Tableau dashboard provides an interactive way to explore these trends and examine how the movie industry has changed between 2000 and 2024.
