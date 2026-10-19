# Airline Passenger Satisfaction Analysis

An exploratory data analysis (EDA) project built with **R** to examine airline passenger satisfaction, service ratings, customer loyalty, travel class, flight distance, and flight delays.

## Project Overview

This project uses R to clean and analyze an airline passenger satisfaction dataset. It produces summary statistics and visualizations that can help identify service areas associated with passenger satisfaction.

### Analysis included

- Check for missing values and fill missing arrival-delay values with `0`.
- Convert the `satisfaction` target into a binary value:
  - `1` = satisfied
  - `0` = neutral or dissatisfied
- Check the target-class proportions.
- Remove the `X` and `id` columns.
- Scale selected service-rating columns from the 0–5 range to the 0–1 range.
- Calculate:
  - Satisfaction percentages
  - Average passenger age by travel class
  - Average ratings for service categories
  - Average departure and arrival delays
  - Number of flights with zero departure delay
  - Satisfaction rates by travel class and customer type
- Generate four charts:
  1. Satisfaction rate by customer type
  2. Satisfaction counts by travel class
  3. Correlation heatmap for service ratings
  4. Flight-distance distribution by satisfaction

## Tools and Libraries

- **R**
- `tidyverse` — data manipulation and plotting
- `reshape2` — reshape the correlation matrix for the heatmap

## Dataset

The project brief references the **Airline Passenger Satisfaction** dataset on Kaggle:

https://www.kaggle.com/datasets/teejmahal20/airline-passenger-satisfaction

Download the dataset from Kaggle and place the appropriate CSV file in the project folder. The current script reads a file named `test.csv`, so either name your input file `test.csv` or update this line in `project_code.R`:

```r
df <- read.csv("test.csv")
```

Use the dataset version that contains the columns referenced by the script, including `satisfaction`, `Arrival.Delay.in.Minutes`, `Departure.Delay.in.Minutes`, `Class`, `Age`, `Customer.Type`, `Flight.Distance`, and the listed service-rating columns.

## Project Structure

```text
airline-passenger-satisfaction-analysis/
├── project_code.R
├── test.csv                  # Add the dataset locally; see data note below
├── README.md
└── visualizations/            # Created by the R script
    ├── Satisfaction rate by Customer Type (Bar Chart).png
    ├── Satisfaction by Class (Grouped Bar Chart).png
    ├── Heatmap of correlations.png
    └── Distribution of Flight Distance.png
```

The `visualizations/` folder is created by the script. The four PNG files are saved when the script runs successfully.

## How to Run

1. Install R: https://cran.r-project.org/
2. (Optional) Install RStudio: https://posit.co/download/rstudio-desktop/
3. Download the dataset and put the required CSV file in the same folder as `project_code.R`.
4. Open R or RStudio and set the working directory to the project folder.
5. Install the required packages once:

   ```r
   install.packages("tidyverse")
   install.packages("reshape2")
   ```

6. Run the script:

   ```r
   source("project_code.R")
   ```

7. Review the printed summaries and check the `visualizations/` folder for the generated charts.

## Important Notes

- The script currently replaces missing `Arrival.Delay.in.Minutes` values with `0`. This treats missing arrival delays as zero delay, which may affect the analysis; consider using median imputation if appropriate for your project.
- The script removes columns named `X` and `id`. If your CSV has different column names, update the `select()` line to match your dataset.
- The rating normalization assumes the selected ratings use a 0–5 scale.
- The current script creates charts and summary statistics; it does **not** train a machine-learning prediction model.
- The dataset is not included in this README. Check the dataset's Kaggle terms and licensing before redistributing it. If you do not have permission to share the data, upload your code and provide the dataset link instead.

## Data Source

Teejmahal20, **Airline Passenger Satisfaction**, Kaggle:  
https://www.kaggle.com/datasets/teejmahal20/airline-passenger-satisfaction

## Author

Add your name and relevant details here.

- Name: `Abhishek Singh`
- Course: `MCA – Data Analytics`
- Project: `Airline Passenger Satisfaction Analysis`
