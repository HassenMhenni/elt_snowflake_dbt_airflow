
# Building My ELT Pipeline with dbt, Snowflake, and Airflow

I'll walk you through how I built an ELT (Extract, Load, Transform) pipeline using dbt, Snowflake, and Airflow. This project showcases my ability to set up and manage a complex data workflow, which is a key highlight in my portfolio.

## 1. Setting Up My Snowflake Environment

I started by configuring my Snowflake environment, which is the backbone of this ELT pipeline.

- **Creating Accounts and Roles:** I created a new warehouse, database, and role within Snowflake. This setup is crucial for organizing and managing the data and resources effectively.

- **Assigning Permissions:** I granted the necessary permissions to my role, ensuring it had the appropriate access to the warehouse and database.

- **Schema Setup:** Finally, I created a schema to logically organize my tables and views within the database.

## 2. Configuring dbt Profiles

Next, I configured dbt to connect to my Snowflake database.

- **Profile Configuration:** In the `dbt_profile.yaml` file, I specified the connection details, including the warehouse, database, and schema.

- **Materialization Strategy:** I defined how dbt should materialize my models, choosing to create views for staging models and tables for marts.


## 3. Creating Source and Staging Models

With dbt connected, I moved on to defining my data sources and creating staging models.

- **Defining Sources:** I specified where my raw data comes from, including the database, schema, and tables in the source files.

- **Building Staging Models:** I created staging models to clean and prepare the raw data. These models are the foundation for my transformations.



## 4. Using Macros for Reusability

To make my code more efficient, I used dbt macros.

- **Creating a Macro:** I created a macro to calculate discounted amounts for order items, which I reused across different models. This approach reduced repetition and ensured consistency.


## 5. Building Intermediate and Fact Tables

Next, I transformed my staged data into more meaningful insights by creating intermediate and fact tables.

- **Intermediate Tables:** These tables further refined my staged data, often involving joins and additional calculations.

- **Fact Tables:** The fact tables provided a comprehensive view of business metrics, such as sales and revenue.


## 6. Implementing Data Quality Tests

Ensuring data quality was a priority, so I set up tests within dbt.

- **Generic Tests:** I used predefined tests to check for common issues like unique and non-null columns.

- **Singular Tests:** I also created custom tests tailored to my specific data models, ensuring everything was accurate and reliable.

## 7. Deploying the Pipeline on Airflow

Finally, I deployed my dbt models using Airflow.

- **Docker Configuration:** I updated my Docker environment to include dbt and other dependencies, ensuring a smooth setup.

- **Airflow DAG:** I created an Airflow DAG to schedule and orchestrate the execution of my dbt models. This ensures that my data transformations run regularly.

- **Connecting to Snowflake:** I set up a secure connection to Snowflake in the Airflow UI, allowing Airflow to interact with my warehouse.

