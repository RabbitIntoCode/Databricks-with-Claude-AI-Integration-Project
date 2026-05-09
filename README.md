# Databricks-with-Claude-AI-Integration-Project

This project demonstrates the integration of Claude AI with Databricks to automate data engineering workflows using natural language prompts. 

By leveraging the Databricks AI Dev Kit and Model Context Protocol (MCP), the solution enables developers to build production-grade ETL pipelines with minimal manual coding.

## Project Overview
Implements Medallion Architecture (Bronze-Silver-Gold) on Databricks Lakehouse Platform

**Technology Stack**

**Platform: Databricks**

**Storage Format: Delta Lake (ACID transactions)**

**Compute: Databricks SQL Warehouses**

**Programming: Python, PySpark, SQL**

**AI Agent: Claude Code (Anthropic Sonnet)**

**CLI Tools: Databricks CLI**

**Development: VS Code, Python venv**

**Protocol: MCP (Model Context Protocol)**

**Version Control: GitHub**

## How It Works

Prompt Parsing: User provides natural language instruction

Skill Retrieval: AI searches AI Dev Kit for relevant patterns

MCP Tool Selection: Identifies appropriate MCP tools

Code Generation: Claude generates PySpark/SQL code

Job Creation: Databricks CLI executes commands

Execution: Jobs run on Databricks compute

Validation: Agent confirms successful execution

## Pipeline Implementation

**Bronze Layer: Source → Raw Data Ingestion**

Prompt: Fetch data from GitHub URLs and create Delta tables in dc_catalog.raw schema. 
Use Python to fetch CSV files and convert to PySpark DataFrames.
Files: bookings.csv, airports.csv, passengers.csv

Outcome:

Automated script: source_to_bronze.py

Databricks Job created for scheduling

Delta tables: dc_catalog.raw.{bookings, airports, passengers}

**Silver Layer: Data Transformation & Enrichment**

Prompt:

Join bronze tables into travel_info in dc_catalog.silver schema.
Joins: bookings ⟕ passengers ON passenger_id
       bookings ⟕ airports ON booking_id
Task: bronze_to_silver.py

Outcome:

Unified dimension: dc_catalog.silver.travel_info
Data quality checks applied
Incremental processing enabled

**Gold Layer: Business Analytics Views**

Prompt:

Create aggregated view counting bookings per city in dc_catalog.gold schema.
Task: silver_to_gold.py

Outcome:

View: dc_catalog.gold.bookings_per_city
Optimized for BI tools and dashboards

## Business Value & Impact

**Productivity Gains**

70% reduction in manual coding effort

Accelerated onboarding through natural language interface

Standardized quality via AI-generated best practices

**Technical Benefits**

Scalable medallion architecture for enterprise lakehouse

ACID compliance via Delta Lake

Reusable AI skills for consistent patterns

Automated job creation and orchestration
