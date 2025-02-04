# Spotify-ETL-Pipeline

## Introduction
This project builds an **ETL (Extract, Transform, Load) pipeline** using the **Spotify API** and AWS cloud services. The pipeline extracts playlist data, transforms it into a structured format, and loads it into an AWS data store for analysis.

## Architecture 

![Architecture Diagram](https://github.com/maimran786/Spotify-ETL-Pipeline/blob/main/Docs/Architecture%20Diagram.png)

### ETL Pipeline Flow

**Extract:** Fetches data from Spotify API.
**Transform:** Cleans, processes, and structures the data.
**Load:** Stores processed data in AWS S3, followed by schema inference and querying

### About Dataset/API

The dataset is sourced from the [Spotify API](https://developer.spotify.com/documentation/web-api) and contains information on:

Music artists
Albums
Songs

### Services Used
1. **Amazon S3 -** Stores raw and transformed data.
2. **AWS Lambda -** Extracts and transforms data automatically.
3. **Amazon CloudWatch -** Monitors and triggers data extraction every hour.
4. **AWS Glue Crawler -** Infers schema for structured storage.
5. **AWS Data Catalog -** Stores metadata for better organization.
6. **Amazon Athena -** Enables SQL-based queries on stored data.

### Install Dependencies

pip install pandas
pip install numpy
pip install spotipy

### Project Execution Flow

**Extract Data from API → Lambda Trigger (every 1 hour) → Run Extract Code  
→ Store Raw Data → Trigger → Transform Data → Load It → Query Using Athena**

### How to Run the Project Locally

#### Clone the Repository(bash):

git clone https://github.com/maimran786/Spotify-ETL-Pipeline.git
cd Spotify-ETL-Pipeline

#### Set up environment variables (AWS & Spotify credentials).

#### Run Extraction Script

python scripts/spotify_api_data_extract.py

#### Run Transformation & Load Script

python scripts/spotify_transformation_load_function.py

#### Query Data in Athena (AWS Console)
