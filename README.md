# Manon - Airflow ETL

============

ETL and analysis are important for data science workflow.
Airflow is different from Apache Beam. It is more oriented
to executing separate steps rather than being fully fledged
data streaming analytics solution.
It has a variety of built-in operators.

---

## Features
- MWAA support
- Redshift support

---

## Setup
Clone this repo:
```
git@github.com:andreiliphd/manon-airflow-etl.git
```


---

## File structure

`setup.ipynb` - Jupyter Notebook for creating tables in Redshift

`udacity_plugin.py` - plugin definition for Apache Airflow

`operators/` - folder with operators for Apache Airflow

`operators/stage_redshift.py` - operator for staging data from S3 before loading to Redshift

`oprators/load_fact.py` - operator for loading fact table to Redshift

`operators/load_dimenstion.py` - operator for loading dimension tables to Redshift

`operators/data_quality` - data quality check operator

`dags/` - folder with dags for Apache Airflow

`requirements.txt` - requirements for running `setup.ipynb`.

---

## Notebook
In a file `setup.ipynb` you can find Jupyter Notebook for setting up tables in Redshift.

---

## Usage
There are two main AWS products involved to successfully execute project:
- MWAA
- Redshift

Steps:
1. Setup Redshift. Don't forget to make publicly available with EIP.
2. Setup MWAA.
3. Upload to S3 `dags/sparkify_dag.py`.
4. ZIP and upload to S3 `operators` folder along with `__init__.py` and `udacity_plugin.py`.
5. Point MWAA to these buckets.
6. Execute cells in `setup.ipynb`.
7. Open MWAA UI and run DAG.


---

## License
This project is licensed under the terms of the **MIT** license.