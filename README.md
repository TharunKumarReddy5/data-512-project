[![MIT License](https://img.shields.io/apm/l/atomic-design-ui.svg?)](https://github.com/tterb/atomic-design-ui/blob/master/LICENSEs)
![contributors](https://img.shields.io/github/contributors/TharunKumarReddy5/data-512-project.svg)
![codesize](https://img.shields.io/github/languages/code-size/TharunKumarReddy5/data-512-project.svg)
![pullrequests](https://img.shields.io/github/issues-pr/TharunKumarReddy5/data-512-project.svg)
![closedpullrequests](https://img.shields.io/github/issues-pr-closed-raw/TharunKumarReddy5/data-512-project.svg)

**Analysis of Google Search Patterns during the COVID-19 pandemic**

Analysis of Google Search Patterns in Milwaukee County, WI during the COVID-19 pandemic
=======================================================================================

This repository contains the the final project documents and code for DATA 512
Human Centered Data Science course project component at the University of
Washington - Masters in Data Science program

Date of Code Run: 2022-12-04

Goal
====================

We have all been affected by a worldwide pandemic for the past three years. This
has had a terrible and disruptive impact on many nations and has had a
significant negative personal impact on many people and their families. The
datafication of the pandemic is one feature that has been difficult to ignore
during the past three years.

data-512-project-common-analysis project is an analysis exercise with primary
goal to understand the general biases in the models that originate from the bias
in the input data used for training the model. This collaborative analysis gives
a good clarity on how the masking policy is impacting the progression of the
COVID virus among various counties in USA. It helps us understand the reasons,
impact and other important factors that directly or indirectly impacted the
COVID infection spread.

County Assigned: Milwaukee County, Wisconsin, United States

Below are the set of Research questions and Hypothesis the study tries to answer:

##### Research Question 1 – How does the Public Mask Mandate in the county impacts the search for all COVID-19 symptoms? 

Hypothesis 1 – Individuals are X% less likely to search for symptoms if the Public Mask Mandate is effective in the county. • The mask mandate decreases the likelihood of searching for any symptoms within the last X days by Y%. 

Research Question 2 – What are the top symptoms strongly impacted by the mask mandate? 

Hypothesis 2 – People are X%, Y%, and Z% less likely to search for fever, chills, and fatigue in Milwaukee County during Mask Mandate 

Research Question 3 - What are the highly correlated symptom search terms with the daily confirmed COVID-19 cases and fatalities before and after the mask mandate policy? 

Hypothesis 3 – “Severe chest pain” positively correlates with COVID-19 fatalities when no mask mandate exists. • A time-lag correlation of X days is observed between the daily number of confirmed cases with the top symptom search terms “cough” and “shortness of breath” during the mask mandate. 

Research Question 4 - How are vaccination intent and side effect search terms correlated with mask mandate policies?

Hypothesis 4 – Individuals showed X% more vaccination intention when the masking mandate was removed in the county

Raw Data Sources
====================

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
========================================

1.  There are few data gaps in the confirmed cases data. To bypass through these
    gaps, rolling averages are used on confirmed cases data. This will eliminate
    any noise that arises in the data due to data collection issues

2.  For milwaukee county, the mask usage survey was conducted before the masking
    mandate was in place. Hence, these % values shouldn't be taken at face value
    when inferring the impact of masking on the infection spread

Human-Centered Considerations
========================================

All the proposed analysis methods in the current study are designed with human-centeredness in mind. Firstly, the proposed design for the study is people-centered. It embeds the end users' thoughts and concerns about the symptoms and vaccines, leveraging them to develop policy health care changes for citizens. It leverages the data produced by the people for the people. 

Secondly, I adopted a participatory design where the data from users' searches is incorporated into the developed solution in real time. This immediate, quick, and cheap feedback will help proactively update the policy suggestions based on the actions performed by the people. Especially for this task, given the anonymity in the virus dynamics and limited knowledge about the nuances in the study, it is critical to give and take inputs in a collaborative cohort setting. 

Thirdly, the design process involves ethical considerations. It uses masked data produced by the people of Milwaukee County and is free of other demographic biases. For the data leveraged by the above three methods proposed, differential privacy has been used by adding artificial noise, enabling high-quality results without identifying anyone. To further protect people's privacy, it is ensured that the study leverages no personal information or individual search queries. 

Finally, the proposed solution of the study is highly reproducible. The methodology proposed can be leveraged to fit any data consisting of people's searches by validating and incorporating the assumptions made in regression and correlation analysis.

Dependencies
====================

Install the dependencies from the requirements.txt file using

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
python -m pip install -r requirements.txt
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Repository Structure
========================================

Here are the main folders in our github data-512-project-common-analysis
repository:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.
├── Tharun DATA 512 Project Part 1.ipynb
├── README.md
├── LICENSE
├── data
│   ├── RAW_us_confirmed_cases.csv
│   ├── RAW_us_deaths.csv
│   ├── mask-mandate-milwaukee.csv
│   └── mask-use-by-county.csv
├── Part1_Reflection_Statement.pdf
├── Part2_VisualizationExplanation.pdf
├── plots
│   ├── cases_per_capita.png
│   ├── derivative_infection_rate.png
│   ├── growth_factor.png
│   ├── infection_rate.png
│   ├── mask_mandate_coverage.png
│   ├── transmission_rate.png
│   └── EDA
│       ├── cases_per_day.png
│       ├── cumulative_cases.png
│       ├── cumulative_deaths.png
│       └── deaths_per_day.png
├── requirements.txt
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Input Data Files
====================

-   RAW_us_confirmed_cases.csv - Consists of daily confirmed COVID cases for all
    counties in USA

-   RAW_us_deaths.csv - Consists of daily fatality count due to COVID for all
    counties in USA

-   mask-mandate-milwaukee.csv - Mask mandate information for the Milwaukee
    county

-   mask-use-by-county.csv - Survey that contains the percent values of mask
    compliance based on level of compliance

Data (Source and Schema)
========================================

The [Education
Statistics](https://datacatalog.worldbank.org/dataset/education-statistics) dataset
being used in this assignment is downloaded from the [World
Bank](http://www.worldbank.org/). The dataset sources it's data from:

1.  UIS ([UNESCO Institute for Statistics](http://uis.unesco.org/)) -
    Administrative country data

2.  Several International and Regional learning assessments

3.  [World Bank Education Projects
    Database](http://datatopics.worldbank.org/education/wQueries/qprojects) -
    activities, components and sub-sectors of WB Education projects since 1998

4.  [World Bank Education Expenditures
    Database](http://datatopics.worldbank.org/education/wQueries/qexpenditures) -
    Education expenditure data

The datasets have been downloaded and added to
the [data](https://github.com/CoderHam/data-512-final-project/tree/master/data) directory
and consists of 5 parts that have been described below, plus one additional
dataset for income groups:

[EdStatsCountry.csv](https://github.com/CoderHam/data-512-final-project/tree/master/data/EdStatsCountry.csv)

 

Results Summary
---------------

### Screenshots

Examples of output plots generated by the functions. Also mentioned the
inference drawn from various metrics calculated using the provided COVID data
for milwaukee county. These metrics were compared against the masking mandate
policy implemented. Below are few of the findings.

-   **Screenshot of plot 1:** Incidence Rate or Positive Per capita Plot

The first graph contains the positive cases per capita rate and it's progression
with respect to masking policy changes

[Image1](https://github.com/TharunKumarReddy5/data-512-project-common-analysis/blob/main/plots/cases_per_capita.png)

![Alt text](https://github.com/TharunKumarReddy5/data-512-project-common-analysis/blob/main/plots/cases_per_capita.png)

**Inference:** We can observe that after the before the mask mandate is
enforced, the spread category is uncontrolled (red band) indicating the
necessity for a mask mandate. Post the mask mandate is implemented, we can
notice that the phase shifted into a controlled band (orange) and stayed for 60
time intervals (2 months). The same trend can be observed before the masking
mandate end. However, the impact of removing the mandate can be seen in the next
30 time intervals (1 month). This shows a clear impact of masking on the
positive cases per capita in milwaukee.

-   **Screenshot of plot 2:** Growth Factor Plot

The second graph contains the growth factor and it's progression with respect to
masking policy changes

[Image2](https://github.com/TharunKumarReddy5/data-512-project-common-analysis/blob/main/plots/growth_factor.png)

![Alt text](https://github.com/TharunKumarReddy5/data-512-project-common-analysis/blob/main/plots/growth_factor.png)

**Inference:** The growth factor plot shows a clear indication of how the GF
values have died down after the mask mandate started and the impact lasted for
almost 2 months before it spiked again during the next wave of COVID. High
growth factor values are again observed after the mask mandate was relaxed in
April 2021.

-   **Screenshot of plot 3:** Transmission Rate Plot

The third graph contains the virus transmission rate and it's progression with
respect to masking policy changes

[Image3](https://github.com/TharunKumarReddy5/data-512-project-common-analysis/blob/main/plots/transmission_rate.png)

![Alt text](https://github.com/TharunKumarReddy5/data-512-project-common-analysis/blob/main/plots/transmission_rate.png)

**Inference:** In the plot, we can observe that transmission rate has gone down
after the masking mandate has started. This also indicates how the spread of the
virus has gone down after people following the mandate. However, the
transmission rate peaked immediately after the mandate is removed but came down
after a month. This can be because of the vaccination phase that started and
implementing second doses to mass population.

-   **Screenshot of plot 4:** Infection Rate Plot (with changepoints)

The fourth graph contains the infection rate and it's progression with respect
to masking policy changes

[Image4](https://github.com/TharunKumarReddy5/data-512-project-common-analysis/blob/main/plots/infection_rate.png)

![Alt text](https://github.com/TharunKumarReddy5/data-512-project-common-analysis/blob/main/plots/infection_rate.png)

**Inference:** From the 4th change point, we can observe that how the masking
mandate brought down the infection rate. This change shows an evidence of the
impact of masking policy. From the 8th change point to 9th, there is no huge
difference in infection rates. Hence, removing masking policy can be attributed
to the stability. However, at the final change point (10th) the COVID infection
rate started to peak.

-   **Screenshot of plot 5:** Derivative of Infection Rate (with changepoints):

The fifth graph contains the derivate of infection rate and it's progression
with respect to masking policy changes

[Image5](https://github.com/TharunKumarReddy5/data-512-project-common-analysis/blob/main/plots/derivative_infection_rate.png)

![Alt text](https://github.com/TharunKumarReddy5/data-512-project-common-analysis/blob/main/plots/derivative_infection_rate.png)

**Inference:** We can observe that the after 4th change point after the masking
mandate started, the derivate is more closer to 0 indicating the change in
infection rate over time is not frequent. The same pattern can be observed after
removing the mandate but oscillated more at the end.

Overall, it is evident from the above analysis as to why there arose a necessity
for enforcing and removing masking policy. The analysis clearly shows an impact
of masking on infection rate and how it accelerated after the mandate is
removed. However, there are few exceptions where observed, where we see peak
infection rates even after the masking policy is in place. This can be
attributed to high impact of other aspects like vaccinations, recovery rates,
hospitalizations

License for this project
------------------------

-   MIT License(<https://opensource.org/licenses/MIT>)

Data set Licensing
------------------

-   The Johns Hopkins data is available under the [creative commons
    license](https://creativecommons.org/licenses/by/4.0/) which means the data
    is available with proper attribution.  
    

-   The CDC data is available under the below citation:  
    CDC, COVID-19 Community Intervention & Critical Populations Task Force,
    Monitoring & Evaluation Team, Mitigation Policy Analysis Unit, the CDC,
    Center for State, Tribal, Local, and Territorial Support, Public Health Law
    Program, and Max Gakh, Assistant Professor, School of Public Health,
    University of Nevada, Las Vegas, “U.S. State and Territorial Orders
    Requiring Masks in Public,” (August 15, 2021).  
    

-   The New York Times mask data is available under this [permissive
    license](https://github.com/nytimes/covid-19-data/blob/master/LICENSE) which
    is highly permissive with proper attribution.

Relevant documentation
----------------------

-   [1] Kaggle project <https://www.kaggle.com/ludobenistant/hr-analytics>

-   [2] Latest report from Bureau of
    Labour <https://www.bls.gov/news.release/jolts.nr0.htm>

-   [3] History of business
    intelligence <https://www.betterbuys.com/bi/history-of-business-intelligence/>

-   [4] Article on solving attrition with
    data <https://towardsdatascience.com/solving-staff-attrition-with-data-3f09af2694cd>

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
