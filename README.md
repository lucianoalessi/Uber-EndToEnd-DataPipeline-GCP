# ** Uber end to end data pipeline with GCP | Data Engineering Project | Data Analytics **

## **Introduction**

This project focuses on performing data analysis on Uber trip records by leveraging cloud-based tools and services. The key objective is to build a data pipeline for extracting, transforming, and loading (ETL) data using **Google Cloud Platform (GCP)**, and then visualize insights through **Looker Studio**. We use a combination of **Python**, **Compute Engine**, **Mage** for pipeline orchestration, **BigQuery** for storage and querying, and **Looker Studio** for data visualization.

## **Project Architecture**

![Project Architecture](architecture.jpg)  
The architecture includes data ingestion, processing, and visualization on GCP. The pipeline is orchestrated using Mage, and the data is loaded into BigQuery for further analysis and dashboard creation.

## **Technologies Used**

- **Programming Language**: Python

### **Google Cloud Platform Services**
1. **Google Cloud Storage**: Used to store raw datasets.
2. **Compute Engine**: Used to run the data processing pipeline.
3. **BigQuery**: Data warehouse for storing processed data and running SQL queries.
4. **Looker Studio**: Data visualization tool for building interactive dashboards.

### **Data Pipeline Tool**
- **Mage.ai**: An open-source data pipeline tool for orchestration of ETL processes. You can find more information at [Mage](https://www.mage.ai/).

## **Dataset Information**

### **Dataset**
The project utilizes **TLC Trip Record Data**, which contains detailed records of yellow and green taxi trips in New York City. The fields include:
- Pick-up and drop-off dates/times and locations
- Trip distances
- Itemized fares
- Payment types
- Passenger counts

The dataset used for this project is available in the `data` folder.

- **Official Dataset Website**: [NYC TLC Trip Record Data](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)
- **Data Dictionary**: [TLC Data Dictionary PDF](https://www.nyc.gov/assets/tlc/downloads/pdf/data_dictionary_trip_records_yellow.pdf)

## **Data Model**

The dataset was structured into a dimensional model to support analytical queries. Below is the visual representation of the data model used for transformations and analysis:

![Data Model](data_model.jpeg)

This model includes various dimensions and fact tables necessary to derive insights from the taxi trip records.

## **Pipeline Steps**

### **1. Data Ingestion**
- The raw trip record dataset was uploaded to **Google Cloud Storage**.
- Multiple formats and files were supported, and the data was stored in an organized structure for further processing.

### **2. Pipeline Construction**
- A **Google Compute Engine** instance was set up to run the ETL pipeline.
- Using **Mage.ai**, the pipeline was built with specific blocks for:
  - **Extract**: The raw data was read from Google Cloud Storage.
  - **Transform**: Python scripts were used to clean the data and transform it into the defined dimensional model, structuring the data into various dimensions and fact tables for final loading.
  - **Load**: The cleaned data was written to **Google BigQuery** for analysis.

### **3. Data Loading**
- After transformations, the dataset was loaded into **BigQuery** using Mage's loading block. BigQuery provided a scalable and efficient solution for running SQL queries on large datasets.

### **4. Data Visualization**
- Once the data was available in BigQuery, a new table was created and imported into **Looker Studio**.
- An interactive **dashboard** was designed to display key insights, including metrics such as trip counts, average fare per trip, trip duration, and popular pickup/drop-off locations.

## **Setup Instructions**

### **Prerequisites**
- **Google Cloud Platform (GCP)** account
- Python 3.8+
- **Mage.ai** installed on a Compute Engine instance
- **BigQuery** setup

### **Step-by-Step Setup**
1. Clone the project repository.
    ```bash
    git clone <repository_url>
    cd uber-data-engineering-gcp
    ```

2. Set up a **Google Cloud Storage** bucket and upload the raw dataset.
   
3. Create a **Compute Engine** instance and install **Mage.ai**.

    1. Install Mage

        ```bash
        pip install mage-ai
        ```
    2. Create new project and launch tool
        ```bash
        mage start [project_name]
        ```
    3. Open Mage: open http://localhost:6789 in your browser.


4. Define the ETL pipeline in Mage.ai, with extraction, transformation, and loading blocks.
   
5. Load the processed data into **BigQuery**.

6. Create a **Looker Studio** dashboard by importing data from BigQuery.

### **Running the Pipeline**
- To execute the ETL pipeline, navigate to Mage's UI on the Compute Engine instance and start the pipeline.
- Ensure that the dataset is loaded correctly into **BigQuery**.

### **Visualization**
- Open Looker Studio and link your BigQuery data.
- Build custom reports and share insights via the interactive dashboard.

## **Conclusion**

This project demonstrates the integration of various cloud-based tools for managing and analyzing large datasets efficiently. The complete data pipeline from ingestion to visualization allows for insightful analysis of Uber trip records, highlighting how **GCP** and **Mage** simplify the ETL and data visualization process.
