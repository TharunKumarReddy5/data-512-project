[![MIT License](https://img.shields.io/apm/l/atomic-design-ui.svg?)](https://github.com/tterb/atomic-design-ui/blob/master/LICENSEs)
![contributors](https://img.shields.io/github/contributors/TharunKumarReddy5/data-512-project.svg)
![codesize](https://img.shields.io/github/languages/code-size/TharunKumarReddy5/data-512-project.svg)
![pullrequests](https://img.shields.io/github/issues-pr/TharunKumarReddy5/data-512-project.svg)
![closedpullrequests](https://img.shields.io/github/issues-pr-closed-raw/TharunKumarReddy5/data-512-project.svg)

**Analysis of Google Search Patterns during the COVID-19 pandemic**

Analysis of Google Search Patterns in Milwaukee County, WI during the COVID-19 pandemic
=======================================================================================

About the repository: This repository contains the the final project documents and code for DATA 512 Human Centered Data Science course project component at the University of Washington - Masters in Data Science program

Date of Code Run: 2022-12-04
County Assigned: Milwaukee County, Wisconsin, United States

During any pandemic, individuals seek health information due to media curiosity, their own illness, or the illness of a family member. Health information seeking, also known as infodemiology, has been proposed as another disease surveillance method. During the epidemic, digital media played a massive role in spreading information. In addition to conventional surveillance, digital surveillance (internet) can provide intriguing trends concerning COVID-19's general concerns and aid in improving prediction models. The present digital surveillance analysis is driven by individuals' worries in the face of a pandemic. It is being used to determine the extent to which the Public Mask Mandate can safeguard people from getting COVID-19 symptoms. Google Trends (GT) is a valuable resource that may be used for digital monitoring. It may predict healthcare decisions in real time by following people's search behaviors and recording their worries (symptoms, vaccination availability, eligibility, and side effects). 

Milwaukee is one of Wisconsin's largest counties with the highest number of detected COVID-19 cases. Illness-specific symptom search patterns on GT can alert the county's healthcare system to prepare and allocate resources needed ahead of time. The primary goal of this study is to leverage the GT to understand the trends in Milwaukee County citizens' search patterns for symptoms and correlate this information with the number of cases, fatalities, vaccinations, and impact of the public mask mandate in Milwaukee County. The findings can substantially aid in estimating the need for supplementary monitoring and policy methods and informing real-time public health choices. 

Also, Vaccine hesitancy remains a severe challenge in ending the COVID-19 pandemic. Unfortunately, online platforms can also spread substantial misinformation about vaccines. The secondary goal of the analysis is to leverage the GT to understand the trends in vaccine misinformation and how public acceptance of vaccines changed over time with changes in mask mandate policies. Using this analysis, we can attribute these trends to public attitudes, interests during the varying vaccine availability, misinformation regarding the vaccines leading to a high unvaccinated population, and further target education among the citizens.

The proposed analysis can make the policy changes more human-centered as it indirectly incorporates the participatory design strategy. The epidemiological information about the virus spread in the county alone isn't sufficient to devise an effective plan to attenuate the infection rate and accelerate vaccine administration. Embedding the end users' thoughts and concerns about the pandemic and vaccinations can provide real-time, immediate, quick, and cheap feedback to the algorithms that predict/decide policy changes. For example, local governments can develop a practical vaccine distribution algorithm and make accurate infection predictions if they know the concerns of the citizens of the county. It eliminates the scope for wrong interpretations and provides more transparency to the end users of the algorithms developed specifically for the county. Uncovering these wide ranges of insights while considering the context of virus spread reveals insights about individual behaviors and the relationships between different entities involved in the policy-making process.

Below are the set of Research questions and Hypothesis the study tries to answer:

#### Research Question 1: #### 
How does the Public Mask Mandate in the county impacts the search for all COVID-19 symptoms? 
#### Hypothesis 1: ####
Individuals are X% less likely to search for symptoms if the Public Mask Mandate is effective in the county. • The mask mandate decreases the likelihood of searching for any symptoms within the last X days by Y%. 

#### Research Question 2: #### 
What are the top symptoms strongly impacted by the mask mandate? 
#### Hypothesis 2: ####
People are X%, Y%, and Z% less likely to search for fever, chills, and fatigue in Milwaukee County during Mask Mandate 

#### Research Question 3: #### 
What are the highly correlated symptom search terms with the daily confirmed COVID-19 cases and fatalities before and after the mask mandate policy? 
#### Hypothesis 3: ####
“Severe chest pain” positively correlates with COVID-19 fatalities when no mask mandate exists. • A time-lag correlation of X days is observed between the daily number of confirmed cases with the top symptom search terms “cough” and “shortness of breath” during the mask mandate. 

#### Research Question 4: ####
How are vaccination intent and side effect search terms correlated with mask mandate policies?
#### Hypothesis 4: ####
Individuals showed X% more vaccination intention when the masking mandate was removed in the county

Raw Data Sources
-----------------
### Data Source 1:
- The RAW_us_confirmed_cases.csv file from the [Kaggle repository of John Hopkins University COVID-19 data.](https://www.kaggle.com/antgoldbloom/covid19-data-from-john-hopkins-university?select=RAW_us_confirmed_cases.csv)
- The RAW_us_deaths.csv file from the [Kaggle repository of John Hopkins University COVID-19 data.](https://www.kaggle.com/antgoldbloom/covid19-data-from-john-hopkins-university?select=RAW_us_deaths.csv)
The data is structured as below for both data sets, with multiple columns for each additional day of data (wide format):

| Column name     | Description               |
| --------------- | ------------------------- |
| Province\_State | Province or state         |
| Admin2          | Country                   |
| UID             | Unique identifier         |
| iso2            | Unused geography code     |
| iso3            | Unused geography code     |
| code3           | Unused geography code     |
| FIPS            | Unique 5-digit identifier |
| Lat             | Latitude                  |
| Long\_          | Longitude                 |

### Data Source 2:
The [CDC dataset](https://data.cdc.gov/Policy-Surveillance/U-S-State-and-Territorial-Public-Mask-Mandates-Fro/62d6-pm5i) of masking mandates by county. **THIS DATA IS NOT INCLUDED IN THIS REPOSITORY AS THE FILESIZE WAS TOO LARGE. PLEASE DOWNLOAD IT DIRECTLY FROM THE LINK LOCALLY**

| Column name                       | Description               |
| --------------------------------- | ------------------------- |
| State\_Tribe\_Territory           | State or tribe name       |
| County\_Name                      | County name               |
| FIPS\_State                       | Numeric state identifier  |
| FIPS\_County                      | Numeric county identifier |
| date                              | YYYY-MM-DD format         |
| order\_code                       | Order type                |
| Face\_Masks\_Required\_in\_Public | Boolean identifier        |
| Source\_of\_Action                | Authority                 |
| URL                               | URL                       |
| Citation                          | Citation                  |

### Data Source 3:
The New York Times mask compliance [survey data.]

| Column name | Description                                                     |
| ----------- | --------------------------------------------------------------- |
| COUNTYFP    | Numeric state and county identifier                             |
| NEVER       | Percentage of respondants responding "never" wearing masks      |
| RARELY      | Percentage of respondants responding "rarely" wearing masks     |
| SOMETIMES   | Percentage of respondants responding "sometimes" wearing masks  |
| FREQUENTLY  | Percentage of respondants responding "frequently" wearing masks |
| ALWAYS      | Percentage of respondants responding "always" wearing masks     |

### Data Source 4:
• Data set - [COVID-19 Search Trends symptoms dataset](https://github.com/GoogleCloudPlatform/covid-19-open-data/blob/main/docs/table-search-trends.md)

• Description – The dataset consists of aggregated, anonymized trends in Google searches for more than 400 health symptoms, signs, and conditions, such as cough, fever, and difficulty breathing. The dataset provides a time series for each region, showing the relative volume of searches for each symptom

### Data Source 5:
• Data set - [COVID-19 Vaccination Search Insights](https://github.com/GoogleCloudPlatform/covid-19-open-data/blob/main/docs/table-vaccination-search-insights.md)

• Description - This aggregated, anonymized data shows trends in search patterns related to COVID-19 vaccination. These trends in search patterns are made available with the intention of helping design, target, and evaluate public education campaigns. These trends reflect the relative interest in Google searches related to COVID-19 vaccination.


Issues and Special Considerations
----------------------------------

1.  There are few data gaps in the confirmed cases data. To bypass through these
    gaps, rolling averages are used on confirmed cases data. This will eliminate
    any noise that arises in the data due to data collection issues

2.  For milwaukee county, the mask usage survey was conducted before the masking
    mandate was in place. Hence, these % values shouldn't be taken at face value
    when inferring the impact of masking on the infection spread

Human-Centered Considerations
----------------------------------

All the proposed analysis methods in the current study are designed with human-centeredness in mind. Firstly, the proposed design for the study is people-centered. It embeds the end users' thoughts and concerns about the symptoms and vaccines, leveraging them to develop policy health care changes for citizens. It leverages the data produced by the people for the people. 

Secondly, I adopted a participatory design where the data from users' searches is incorporated into the developed solution in real time. This immediate, quick, and cheap feedback will help proactively update the policy suggestions based on the actions performed by the people. Especially for this task, given the anonymity in the virus dynamics and limited knowledge about the nuances in the study, it is critical to give and take inputs in a collaborative cohort setting. 

Thirdly, the design process involves ethical considerations. It uses masked data produced by the people of Milwaukee County and is free of other demographic biases. For the data leveraged by the above three methods proposed, differential privacy has been used by adding artificial noise, enabling high-quality results without identifying anyone. To further protect people's privacy, it is ensured that the study leverages no personal information or individual search queries. 

Finally, the proposed solution of the study is highly reproducible. The methodology proposed can be leveraged to fit any data consisting of people's searches by validating and incorporating the assumptions made in regression and correlation analysis.

Dependencies
----------------------------------

Install the dependencies from the requirements.txt file using

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
python -m pip install -r requirements.txt
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Repository Structure
----------------------------------

Here are the main folders in our github data-512-project repository:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.
├── README.md
├── LICENSE
├── data
│   ├── Part1 Data.csv
│   ├── US_NJ_34003.csv
│   ├── US_WI_55079.xlsx
│   ├── Vaccination Search Insights.xlsx
│   ├── trends_columns.txt
│   └── trends_columns.xlsx
├── data
│   ├── DATA 512 Project.ipynb
│   ├── Tharun DATA 512 Project Analysis.ipynb
│   └── Tharun DATA 512 Project Experiments.ipynb
├── plots
│   └── Milwaukee_Bucks_logo.svg.png
│   └── correlation
│       ├── cough_correlation.png
│       ├── fever_correlation.png
│       ├── pneumonia_correlation.png
│       ├── pneumonia_correlation_all.png
│       ├── shortness_of_breath_correlation.png
│       ├── shortness_of_breath_correlation_all.png
│       └── sore_throat_correlation.png
│   └── trends
│       ├── cough_trends.png
│       ├── did_percentage_change.png
│       ├── fever_trends.png
│       ├── infection_rate.png
│       ├── pneumonia_trends.png
│       ├── shortness_of_breath_trends.png
│       ├── sore_throat_trends.png
│       └── vaccination_trends.png
│   └── archive
│       ├── cough_14days_correlation.png
│       ├── fever_14days_correlation.png
│       ├── pneumonia_14days_correlation.png
│       ├── shortness_of_breath_14days_correlation.png
│       └── sore_throat_14days_correlation.png
├── submissions
│   └── Part1_Reflection_Statement.pdf
│   └── Part1_VisualizationExplanation.pdf
│   └── Tharun DATA 512 Project Final Report.pdf
│   └── Tharun DATA 512 Project Part 2.pdf
│   └── Tharun DATA 516 Project PechaKucha.pptx
├── requirements.txt
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Findings
---------------

Examples of output plots generated by the functions. Also mentioned the key takewaways from various metrics calculated using the provided COVID and Google Trends data
for milwaukee county. These metrics were compared against the masking mandate policy implemented. Below are few of the findings.

### Change point detection

**Change Points in Infection rate**

The first graph contains the change points detected for the infection rate

[Image1](https://github.com/TharunKumarReddy5/data-512-project-common-analysis/blob/main/plots/infection_rate.png)

![Alt text](https://github.com/TharunKumarReddy5/data-512-project-common-analysis/blob/main/plots/infection_rate.png)

**Inference:** From the 4th change point, we can observe how the masking mandate lowered the infection rate. This change shows evidence of the impact of the masking policy. From the 8th change point to the 9th, there is no considerable difference in infection rates. Hence, removing the masking policy can be attributed to stability. However, at the final change point (10th), the COVID-19 infection rate started to peak.

**Change Points in derivative of Infection rate**

The second graph contains the change points detected for the derivative of the infection rate

[Image2](https://github.com/TharunKumarReddy5/data-512-project-common-analysis/blob/main/plots/derivative_infection_rate.png)

![Alt text](https://github.com/TharunKumarReddy5/data-512-project-common-analysis/blob/main/plots/derivative_infection_rate.png)

**Inference:** We can observe that at the 4th change point after the masking mandate started, the derivate is closer to 0, indicating the change in infection rate over time is not frequent. The same pattern can be observed after removing the mandate but oscillates more at the end. 

**Key Takeaways:** Overall, it is evident from the above analysis the reasons for enforcing and lifting the masking policy took place in Milwaukee County. It indicates the impact of masking on the infection rate by showing how it decelerated after the mandate was enforced and accelerated after the mandate was removed. However, a few exceptions are observed where we see peak infection rates even after the masking policy is in place. This can be attributed to the high impact of other aspects like vaccinations, recovery rates, and hospitalizations.

## Change point detection – Google Symptom Search Trends

**Change Points in COUGH symptom search**

The third graph contains the change points detected for COUGH symptom searches

[Image3](https://github.com/TharunKumarReddy5/data-512-project/blob/main/plots/trends/cough_trends.png)

![Alt text](https://github.com/TharunKumarReddy5/data-512-project/blob/main/plots/trends/cough_trends.png)

**Change Points in FEVER symptom search**

The fourth graph contains the change points detected for FEVER symptom searches

[Image4](https://github.com/TharunKumarReddy5/data-512-project/blob/main/plots/trends/fever_trends.png)

![Alt text](https://github.com/TharunKumarReddy5/data-512-project/blob/main/plots/trends/fever_trends.png)

**Change Points in PNEUMONIA symptom search**

The fifth graph contains the change points detected for PNEUMONIA symptom searches

[Image5](https://github.com/TharunKumarReddy5/data-512-project/blob/main/plots/trends/pneumonia_trends.png)

![Alt text](https://github.com/TharunKumarReddy5/data-512-project/blob/main/plots/trends/pneumonia_trends.png)

**Key Takeaways:** FEVER symptom search term is strongly associated with daily COVID-19 confirmed cases. The change points detected for the FEVER search term closely align with those of the infection rate, concluding that the mask mandates evidently changed the symptom search trends. COUGH is the highest searched symptom with high RSV values but is moderately correlated with confirmed COVID-19 cases. This can be because it is a common symptom; the searches can be associated with other seasonal illnesses.

The PNEUMONIA symptom search term is strongly associated with daily COVID-19 fatalities proving that it is a highly critical health issue that requires immediate hospitalization. For PNEUMONIA, a new set of change points are identified that are inconsistent with those of infection rate and mask mandate changes.

## Regression Inference – Impact of Mask Mandate on Symptom Searches

**Impact of mask mandate on symptom search terms**

The sixth graph contains the impact percentages of the search terms due to mask mandate

[Image6](https://github.com/TharunKumarReddy5/data-512-project/blob/main/plots/trends/did_percentage_change.png)

![Alt text](https://github.com/TharunKumarReddy5/data-512-project/blob/main/plots/trends/did_percentage_change.png)

**Key Takeaways:** SHORTNESS OF BREATH, COUGH and SORE THROAT are the top 3 symptom searches impacted by the mask mandate. SHORTNESS OF BREATH symptom search is highly impacted by the removal of the mask mandate in Milwaukee County (20% greater than another county with a continuous mask mandate). FEVER symptom search growth rate is approximately the same with and without mask mandate. PNEUMONIA symptom search term is the least impacted symptom search with the mask mandate in Milwaukee County.

## Correlation Inference – Change in the association of Symptom Searches over time

**Correlation windows of SHORTNESS OF BREATH symptom search**

The seventh graph contains the correlation heatmap for SHORTNESS OF BREATH symptom search

[Image7](https://github.com/TharunKumarReddy5/data-512-project/blob/main/plots/correlation/shortness_of_breath_correlation_all.png)

![Alt text](https://github.com/TharunKumarReddy5/data-512-project/blob/main/plots/correlation/shortness_of_breath_correlation_all.png)

**Correlation windows of PNEUMONIA symptom search**

The eighth graph contains the correlation heatmap for PNEUMONIA symptom search

[Image8](https://github.com/TharunKumarReddy5/data-512-project/blob/main/plots/correlation/pneumonia_correlation_all.png)

![Alt text](https://github.com/TharunKumarReddy5/data-512-project/blob/main/plots/correlation/pneumonia_correlation_all.png)

**Key Takeaways:** The SHORTNESS OF BREATH search term is strongly correlated with a lag of 4 days when there is no mask mandate. However, this correlation is not seen much during the mask mandate except between the 5th and 8th change point period caused by the 2nd wave of COVID-19 (Red region in the middle of Figure 11a). The PNEUMONIA search term is highly correlated at day 11 with daily fatalities and is not impacted much due to the mask mandate (red regions in Figure 11b). These two figures collectively show the variation in the association between the symptom searches with confirmed cases over time.

## Causal Inference – Vaccination Intent and side-effects

**Vaccination causal inference graph (with change points)**

The ninth graph contains the causal inference graph for vaccination related search trends

[Image9](https://github.com/TharunKumarReddy5/data-512-project/blob/main/plots/trends/vaccination_trends_all.png)

![Alt text](https://github.com/TharunKumarReddy5/data-512-project/blob/main/plots/trends/vaccination_trends_all.png)

**Key Takeaways:** Most of the change points with positive slopes are aligned with the positive news regarding the availability, eligibility, and promotions like coupons announced by the government. Change points at negative sloped are associated with the negative news regarding the side effects and CDC pausing the vaccine administration. News about the COVID-19 variants also strongly impacted the vaccination search trends in Milwaukee County.

License for this project
------------------------

-   MIT License(<https://opensource.org/licenses/MIT>)

Data set Licensing
------------------

-   The Johns Hopkins data is available under the [creative commons license](https://creativecommons.org/licenses/by/4.0/) which means the data is available with proper attribution.

-   The CDC data is available under the below citation: CDC, COVID-19 Community Intervention & Critical Populations Task Force, Monitoring & Evaluation Team, Mitigation Policy Analysis Unit, the CDC, Center for State, Tribal, Local, and Territorial Support, Public Health Law Program, and Max Gakh, Assistant Professor, School of Public Health, University of Nevada, Las Vegas, “U.S. State and Territorial Orders Requiring Masks in Public,” (August 15, 2021).
    
-   The New York Times mask data is available under this [permissive license](https://github.com/nytimes/covid-19-data/blob/master/LICENSE) which is highly permissive with proper attribution.

Relevant documentation
----------------------

-   [1] Change point detection <https://centre-borelli.github.io/ruptures-docs/>

-   [2] Difference-in-Difference <https://en.wikipedia.org/wiki/Difference_in_differences>

-   [3] Sliding Window Time Lagged Cross Correlation <https://towardsdatascience.com/four-ways-to-quantify-synchrony-between-time-series-data-b99136c4a9c9>

-   [4] Granger Test <https://en.wikipedia.org/wiki/Granger_causality>

Code Style
----------

Languages used: Python Coding Style: - PEP 8 - Docstrings

Following sofware design principles have been considered while packaging MLPA:

-   Modular design

    -   *'Somewhat General Purpose'* module

    -   Deep Modules

    -   Separation of Concerns

-   Reusability/Extensibility

-   Intuitable

-   Exception Handling

Authors
-------

-   [Tharun Kumar Reddy Karasani](https://github.com/TharunKumarReddy5)

![GitHub Contributors Image](https://contrib.rocks/image?repo=TharunKumarReddy5/data-512-project-common-analysis)

Contribute
----------

This project is an open-source project- open to the Python user community for
contribution.
