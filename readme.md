## UK National Rail Performance 2024 - Capstone Project

**Contributors:** Brian Levesque, Ilackkeya Bhavananthi, Osman Nayeem

**Instructor:** James-Lee Meredith

**Teaching assistant**: Dylan Gleason 

**Program Manager**: William Westley

**Institution:** Grand Circus

**Project Dates** 2nd July 2024 - 18th July 2024

### Description

Welcome to our Repository! This repository hosts our Grand Circus's Final Capstone Project on Data Analytics and Engineering. The project has extensive data engineering and data analytics workflows which is essentially built to analyze the UK National Rail Schedule Performance. Our Client, **UK National Railway Board of Directors** wanted to understand the UK National Schedule Performance, delay compensation efficiency of Train Operating Companies (TOCs) in enhancing user experience and build a predictive model to predict any delay of a scheduled train.

As Data Analysts, we gathered essential data from [UK National Rail Data Portal](https://opendata.nationalrail.co.uk/) accessing API’s Darwin feed and additional data from [ORR](https://dataportal.orr.gov.uk/) and [Network Rail](https://www.networkrail.co.uk/) to do our analysis. We developed a scalable data pipeline architecture using Kafka and Docker, hosted the live-streaming data (after necessary transformation steps) in AWS-RDS PostgreSQL database and performed comprehensive data ingestion, pre-processing and analysis to interpret the key insights.

### Dependencies

1. Data Pipeline tools: Docker, Apache Kafka, Apache Spark
2. Database: AWS-RDS & PostgreSQL
3. Python: sqlalchemy, psycopg2, json, glob, xml.etree.ElementTree, logging, time, pandas, Numpy, datetime, matplotlib, seaborn, warnings, OSGB36toWGS84 from bng_latlon, sklearn
4. PowerBI

### Workflow

Data Collection Period: 07/03/2024 - 07/11/2024

#### 1. **Setting up Data Pipeline**

Docker images for the following applications have been built and docker container was composed to start the pipeline each of which performs the following functions:

**Kafka Zookeeper**: A service necessary for running the Kafka broker. It helps in maintaining the configuration information and provides distributed synchronization.

**Kafka Broker**: The heart of the Kafka system that maintains the published data. Each Kafka broker can handle terabytes of messages without performance impact.

**Kafka Producer (Python)**: This application pulls data from the National Rail APIs and publishes it to Kafka. It's designed to run indefinitely, continually pulling and publishing data.

**Kafka Consumer (Spark)**: A Spark application that consumes data from Kafka, processes it and writes the result to a PostgreSQL database.

**PostgreSQL Database (db)**: Stores the processed data from the Spark consumer for later analysis.

#### 2. **Ingesting Data and Pre-processing**

Retrieved data from PostgreSQL database and performed necessary Data Ingestion and Pre-processing and the cleaned data was exported into csv for further data visualizations in PowerBI ([UK National Rail Data_Analysis_Final.ipynb](https://github.com/BrianLevesque/GC_CapstoneProject/blob/feature-ilackkeya/UK%20National%20Rail%20Data_Analysis_Final.ipynb)).

#### 3. **Predictive Analytics**

Built a predictive analytics model on predicting the delay using Logistic Regression model yielding an accuracy of 91.25%.  

#### 4. **Data Visualizations**

Gathered visual insights utilizing matplotlib, seaborn libraries and Power BI ([UK National Rail Performance Overview.pbix](https://github.com/BrianLevesque/GC_CapstoneProject/blob/feature-ilackkeya/UK%20National%20Rail%20Performance%20Overview.pbix)) to answer our questions. 


#### Key Insights and Recommendations:

**#### Delay Metrics:**

**Overall(%)**: 8.7%

**Time of the day**: Between 2AM & 3AM

**Day of the week**: Alternate days of the week

**Most Delayed Platforms**: UM at Chester-le-Street and 15A at Leeds Rail Stations

**Impact of Train Length**: None

**Are Longer Journey Trains affected?** Yes, journey time > 150 mins see significant delay in arrival/departure

**Are Busiest Stations experiencing more delays?** No, they experience delay < 10 mins.

**Most delayed TOC**: London North Eastern Railways (from our data collected)

![image](https://github.com/user-attachments/assets/2f2be32f-5af5-4749-9bdd-86ae76bc721f)

![image](https://github.com/user-attachments/assets/bf016e34-e352-43d2-bad4-c868d4188414)

**#### Delay Compensation Analysis**

![image](https://github.com/user-attachments/assets/143ca8c9-b9ad-4b38-964f-7a2652ea7e2c)

London North Eastern Railways has closed 96.7% of delay compensation claims in the last of 5 years ensuring customer satisfaction and user experience

**Delay Compensation Efficiency of TOCs**: Cannot be determined, due to the non-uniform delay compensation policies set forward by the TOCs has hindered the assessment of their customer service efficiency in improving user experience.

**Delay Prediction Model**: Model built with an accuracy of 91.25% with journey time being the most influencing factor in delay prediction.


**#### Recommendations:**

The clients can implement standardized guidelines for delay compensation claims across all operators, ensuring consistent and fair customer service while enhancing the user experience in railway transportation.


### For more information

Please review the directed links or [pdf](https://github.com/BrianLevesque/GC_CapstoneProject/blob/feature-ilackkeya/UK%20National%20Rail%20Data_Analysis_Final.pdf) or [PPTX](https://github.com/BrianLevesque/GC_CapstoneProject/blob/feature-ilackkeya/UK%20National%20Rail%20Performance%202024.pptx) files.

If you have any questions or feedback, please feel free to reach out to any of the authors.

- Brian Levesque brian.lev722@gmail.com

- Ilackkeya Bhavananthi bsilackkeya21@gmail.com

- Osman Nayeem osman_nayeem@yahoo.com 


