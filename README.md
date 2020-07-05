# airflow_pipelines

 ***Credits***
Udacity Data Engineer Nanodegree Program

## Rubric

General

- [x] ***The dag and plugins do not give an error when imported to Airflow***: DAG can be browsed without issues in the Airflow UI

- [x] ***Staging tables are properly defined***: The dag follows the data flow provided in the instructions, all the tasks have a dependency and DAG begins with a start_execution task and ends with a end_execution task.

Dag configuration

- [x] ***Default_args object is used in the DAG***: DAG contains default_args dict, with the following keys:
Owner
Depends_on_past
Start_date
Retries
Retry_delay
Catchup

- [x] ***Defaults_args are bind to the DAG***: The DAG object has default args set

- [x] ***The DAG has a correct schedule***: The DAG should be scheduled to run once an hour

Staging the data

- [x] ***Task to stage JSON data is included in the DAG and uses the RedshiftStage operator***: There is a task that to stages data from S3 to Redshift. (Runs a Redshift copy statement)

- [x] ***Task uses params***: Instead of running a static SQL statement to stage the data, the task uses params to generate the copy statement dynamically

- [x] ***Logging used***: The operator contains logging in different steps of the execution

- [x] ***The database connection is created by using a hook and a connection***: The SQL statements are executed by using a Airflow hook

Loading dimensions and facts

- [x] ***Set of tasks using the dimension load operator is in the DAG***: Dimensions are loaded with on the LoadDimension operator

- [x] ***A task using the fact load operator is in the DAG***: Facts are loaded with on the LoadFact operator

- [x] ***Both operators use params***: Instead of running a static SQL statement to stage the data, the task uses params to generate the copy statement dynamically

- [x] ***The dimension task contains a param to allow switch between append and insert-delete functionality***: The DAG allows to switch between append-only and delete-load functionality

Data Quality Checks

- [x] ***A task using the data quality operator is in the DAG and at least one data quality check is done***: Data quality check is done with correct operator

- [x] ***The operator raises an error if the check fails pass***: The DAG either fails or retries n times

- [x] ***The operator is parametrized***: Operator uses params to get the tests and the results, tests are not hard coded to the operator