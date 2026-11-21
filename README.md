# data-analyst project

A Python-based exploratory data analysis (EDA) project that studies
domestic flight ticket prices in India and explores how distance,
booking lead time, travel class, booking channel, and airline type
relate to the price paid by passengers.

## Project Overview

The project is framed from the perspective of a pricing and revenue team
at an online travel platform. The goal is to understand ticket-price
patterns, identify factors associated with higher or lower prices, and
highlight bookings that may deserve closer attention.

**Project folder:** `data-analyst-project`

## Business Problem

An online travel platform wants to understand what drives the prices
customers pay for domestic flight tickets. Insights into distance,
booking lead time, travel class, and airline type can help the platform:

-   Understand the overall distribution of ticket prices.
-   Explore factors associated with higher or lower ticket prices.
-   Compare prices across cities and booking categories.
-   Identify high-value and budget bookings for further investigation.

## Dataset

The analysis uses a dataset of one-way domestic flight bookings in
India, with one row representing one booking.

  Detail            Description
  ----------------- ---------------------------
  Raw file          `flight_data.csv`
  Cleaned file      `flight_analysis_final.csv`
  Raw records       255
  Cleaned records   250
  Columns           11
  Currency          Indian Rupees (INR)

### Data Dictionary

  -----------------------------------------------------------------------
  Column                              Description
  ----------------------------------- -----------------------------------
  `Booking_ID`                        Unique booking identifier

  `Booking_Date`                      Date on which the ticket was booked

  `Source_City`                       City from which the flight departs

  `Travel_Class`                      Cabin class: Economy, Premium
                                      Economy, or Business

  `Booking_Channel`                   Booking source: Mobile App,
                                      Website, or Travel Agent

  `Airline_Type`                      Low-cost or full-service airline

  `Distance_Km`                       Flight distance in kilometres

  `Days_Before_Departure`             Number of days between booking and
                                      departure

  `Passenger_Age`                     Passenger age in years

  `Baggage_Kg`                        Checked baggage weight in kilograms

  `Ticket_Price_INR`                  Ticket price in Indian Rupees; the
                                      outcome variable
  -----------------------------------------------------------------------

## Project Questions

The analysis is organised around four questions:

1.  **Overall price distribution:** What are the average, median,
    spread, minimum, maximum, and distribution shape of ticket prices?
2.  **Distance and booking lead time:** How are `Distance_Km` and
    `Days_Before_Departure` related to `Ticket_Price_INR`? What are the
    direction and strength of these relationships?
3.  **Category-wise price comparison:** How does the average ticket
    price vary by `Source_City`, `Travel_Class`, `Booking_Channel`, and
    `Airline_Type`?
4.  **Bookings needing attention:** How many bookings are High-Value
    (above ₹6,000) and Budget (below ₹2,500), and what characteristics
    do these groups share?

## Data Cleaning

The raw dataset was checked and cleaned before analysis. The cleaned
dataset contains **250 rows and 11 columns**, with **no missing values
and no duplicate rows**.

The cleaned data is saved as `flight_data_cleaned.csv`.

## Analysis and Key Findings

### 1. Overall Ticket Price

  Metric                    Result
  -------------------- -----------
  Mean                   ₹4,093.20
  Median                    ₹3,865
  Minimum                   ₹1,800
  Maximum                  ₹10,200
  Standard deviation     ₹1,895.63
  Skewness                  0.6555

The mean is higher than the median, and the positive skewness indicates
a right-skewed price distribution. In this dataset, some higher-priced
bookings pull the average above the median.

A histogram was used to visualise the distribution of ticket prices.

### 2. Distance and Booking Lead Time

The correlation analysis produced the following results:

  Variable                    Correlation with ticket price Direction
  ------------------------- ------------------------------- -----------
  `Distance_Km`                                    0.567505 Positive
  `Days_Before_Departure`                         -0.432487 Negative

**Interpretation:**

-   `Distance_Km` has a moderate positive relationship with ticket
    price: longer flights tend to be associated with higher ticket
    prices.
-   `Days_Before_Departure` has a moderate negative relationship with
    ticket price: bookings made further in advance tend to be associated
    with lower prices in this dataset.

Correlation describes association; it does not by itself establish
causation.

### 3. Category-wise Price Comparison

The project compares ticket prices across:

-   Source city
-   Travel class
-   Booking channel
-   Airline type

Group-wise average prices and charts are used to make these category
comparisons. Add the final category-wise observations here after
reviewing the generated outputs.

### 4. High-Value and Budget Bookings

Bookings are classified using the project thresholds:

-   **High-Value:** `Ticket_Price_INR` greater than ₹6,000
-   **Budget:** `Ticket_Price_INR` less than ₹2,500

The two groups are examined by their booking and flight characteristics.
Add the final group counts and observed patterns here from the completed
Q4 output.

## Tools and Libraries

-   **Python** --- data analysis
-   **Pandas** --- data loading, cleaning, transformation, and grouping
-   **NumPy** --- numerical operations
-   **Matplotlib** --- data visualisation
-   **Seaborn** --- statistical visualisation, if used in the notebook
-   **Jupyter Notebook / VS Code** --- development environment

## Suggested Project Structure

``` text
data-analyst-project/
│
├── .venv/
│
├── data/
│   ├── processed/
│   │   └── flight_analysis_final.csv
│   │
│   └── raw/
│       └── flight_data.csv
│
├── images/
|   ├── question 1.png
|   ├── question 2.png
|   ├── question 3.png
│   └── question 4.png
│
├── notebooks/
│   └── draft1.ipynb
│
├── script/
│   ├── ppt.pptx
│   └── src_document
│
├── README.md
│
└── requirement.txt
```

Keep the filenames in this structure aligned with the files in your
actual repository.

## How to Run the Project

1.  Clone or download this repository.

2.  Open the project folder in VS Code or Jupyter Notebook.

3.  Install the required libraries:

    ``` bash
    pip install pandas numpy matplotlib seaborn jupyter
    ```

4.  Open the analysis notebook.

5.  Run the notebook cells in order.

## Conclusion

This project uses exploratory data analysis to understand domestic
flight ticket prices in India. The completed numerical analysis shows
that distance is positively associated with ticket price, while booking
lead time is negatively associated with ticket price. The category
comparisons and booking-segment analysis provide additional ways to
investigate differences between bookings.

The results describe patterns in this dataset and should not be treated
as proof that any single factor causes a ticket price to change.

## Author

**Saiyam Gupta**
**2026B01010284**

------------------------------------------------------------------------

*Academic data analysis project. The dataset is used for learning and
exploratory analysis.*
