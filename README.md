# dbt-fundamentals-studios
dbt Fundamentals (dbt studios) course walkthrough

dbt package hub: hub.getdbt.com 

Using codegen package to generate sources and models from the data platform to dbt.
https://learn.getdbt.com/courses/dbt-fundamentals

## Building Your First Model

### Learning Objectives
* Explain what models are in a dbt project.
* Build your first dbt model.
* Explain how to apply modularity to analytics with dbt.
* Modularize your project with the ref function.
* Review a brief history of modeling paradigms.
* Identify common naming conventions for tables.
* Reorganize your project with subfolders.

**Steps:**

1. Initialize a dbt project.
2. Example models are created after the initialization.
3. run `dbt run` command to create the models in data platform.
4. Created `customers.sql` model in dbt.

**Notes:**

1. Models are created as view by default in dbt.
2. Models can be materialized as tables if mentioned in the model or dbt_project profile.
3. Priority is given to materialization in the model.

Syntax to config materialization in model:

{{ config(materialized='...')}}

**above is a jinja function used in dbt.**

#### ref function in dbt
1. Helps to reference a model in dbt dynamically.
2. Provide lineage for the model when used in it.

**Notes**
1. ref provides order of execution when dbt run in called for the model creation.
2. '+' symbol is used to identify the building process in dbt with using run or build command

`dbt run --select model` normal run

`dbt run --select +model` upstream run

`dbt run --select model+` downstream run

`dbt run --select +model+` upstream and downstream run

## Understanding Sources

* Explain the purpose of sources in dbt.
* Configure and select from sources in your data platform.
* View sources in the lineage graph.
* Check the last time sources were updated and raise warnings if stale.

## Building Tests

* Explain why data testing is crucial for analytics.
* Explain the role of data testing in analytics engineering.
* Configure and run generic tests in dbt.
* Write, configure, and run singular tests in dbt.

**Notes**
* Execute dbt test to run all generic and singular tests in your project.
* Execute dbt test --select test_type:generic to run only generic tests in your project.
* Execute dbt test --select test_type:singular to run only singular tests in your project.

## Documentation Basics

* Explain why documentation is crucial for analytics.
* Understand the documentation features of dbt.
* Write documentation for models, sources, and columns in .yml files.
* Write documentation in markdown using doc blocks.
* View and navigate the lineage graph to understand the dependencies between models.

## Understanding Deployment

* Understand why it's necessary to deploy your project.
* Explain the purpose of creating a deployment environment.
* Schedule a job in dbt.
* Review the results and artifacts of a scheduled job in dbt.