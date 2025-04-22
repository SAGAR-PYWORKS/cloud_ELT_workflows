# CLOUD_ELT_workflows
## Cloud-based Data Processing and Transformation Workflow

This task involves designing and implementing a data pipeline across the Azure and Databricks ecosystem with Snowflake integration for analytics-ready data.

Source Ingestion:
Data is initially ingested from the Azure Data Lake Storage (ADLS) Bronze container.
The raw data is loaded into Databricks DBFS for processing.

Data Cleaning (Bronze → Silver):

  
<li>Perform data cleaning tasks within Databricks:
  <ol>
    <li>Handle null values.</li>
    <li>Remove trailing and leading spaces.</ul>
    <li>Convert text columns to uppercase.</ul>
    <li>Clean and format numerical columns.</ul>
    <li>Standardize the date formats.</ul>
    <li>The cleaned data is stored in the Azure Silver container.</ul>
  </ol>
</li>


<li>Data Transformation (Silver → Gold):
<ol>
  <li>Read cleaned data from the Silver container.</ul>
  <li>Apply business-level data transformations and logic.</ul>
  <li>Store the final, transformed data into the Azure Gold container.</ul>
</ol>
</li>

<li>Automated Snowflake Loading:
<ol>
  <li>A topic listener (event-driven mechanism) is implemented to monitor the Gold container.</ul>
  <li>As soon as new data lands in the Gold container, the listener triggers the pipeline to automatically load the data into the Snowflake target table.</ul>
</ol>
</li>
