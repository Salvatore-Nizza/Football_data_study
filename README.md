**Project Title:** Analysis of Expected Assists from Corner Kicks in Serie A 2021-2022

**Description:**
This project uses positional event data to develop a simplified **logistic regression model** to estimate **expected assists (xA)** derived from corner kicks. The analysis focuses on the **2021-2022 Serie A season**. The model aims to identify corner kick situations that offer the greatest offensive advantage.

**Datasets Used:**
*   **SICS positional data from corner kicks:** The main dataset contains positional data related to corner kicks in Serie A 2021-22.
*   **Preferred foot database:** Contains information on players' preferred foot, useful for classifying crosses.
*   **Player ID dataset:** Contains player IDs, used for merging datasets.

**Project Structure:**
The project is divided into several main phases:

1.  **Data Preparation:**
    *   Importing and cleaning data from various sources.
    *   Creating a unified dataset by merging the datasets.
    *   Selecting events of interest, i.e., corner kicks.
2.  **Classification of Corner Kicks:**
    *   Corner kicks are classified into four groups (A, B, C, D) based on the position of the corner kick (right or left) and the preferred foot of the player making the cross.
    *   Group A: right corner, right foot (outswinging cross)
    *   Group B: right corner, left foot (inswinging cross)
    *   Group C: left corner, left foot (outswinging cross)
    *   Group D: left corner, right foot (inswinging cross)
3.  **Model Implementation:**
    *   Development of a logistic regression model to estimate expected assists.
    *   The model is **shot-centric**, meaning the assist is linked to the shooter receiving the pass.
    *   The predictive variables used in the model are **distance and angle to the goal**.
4.  **Data Analysis:**
    *   Model evaluation using **ROC AUC score**.
    *   Analysis of the correlation between expected assists and actual assists.
    *   Comparison of results between different groups of corner kicks.
    *   Analysis of the probabilistic precision of the model.
    *  Analysis of the conversion rate as a function of the distance and angle to the goal.

**Python Libraries Used:**
*   **pandas:** For data manipulation and analysis.
*   **numpy:** For mathematical operations.
*   **seaborn:** For data visualization.
*   **matplotlib.pyplot:** For creating charts.
*   **scipy:** For statistical and interpolation functions.
*   **sklearn.linear_model:** For implementing the logistic regression model.
*   **sklearn.metrics:** For model evaluation.
*   **mplsoccer:** For visualizing soccer fields and heatmaps.
*   **highlight_text:** For highlighting text in charts.

**Key Results:**
*   Corner kicks with **inswinging crosses (Groups B and D) generate a greater offensive benefit** in terms of assists compared to those with outswinging crosses (Groups A and C).
*   The model, despite some limitations, is able to describe expected assists in a summary manner.
*   The **ROC AUC values** show that the model is quite reliable.
*   The model has good probabilistic precision.
*   There is a **linear correlation** between the values of the expected assist model and the actual assists.
*   The model can be improved by training it on a larger dataset and considering other dependency parameters.

**Future Improvements:**
*   Increase the database with previous seasons and/or other leagues.
*   Consider additional parameters such as the position of the players on the field.
*   Analyze the position of the opposing team's players.

**Important Notes:**
*   The positional data was normalized.
*   The expected assist model is considered similar to the expected goal model.
*   It was assumed that all the passes considered came from corner kicks.
