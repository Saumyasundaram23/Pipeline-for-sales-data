# Google Cloud Data Analytics Project

This repository contains code and configuration files for Google Cloud Data Analytics Project.This project demonstrates the integration of several GCP services to create an efficient and automated data pipeline for sales data. We'll show you how to:


Refer youtube Video for this project
 [![YouTube](https://img.shields.io/badge/YouTube-Video-red)](https://youtu.be/_CQCOusfGrs)


![image](https://github.com/vishal-bulbule/sales-data-pipeline-project/assets/143475073/530f2c9e-945c-414c-8c85-5b489e92360e)



## Overview

1. **Web Portal**: Built with Python Flask to allow users to upload sales data files.
2. **Storage**: Uploaded files are stored in a GCS bucket.
3. **Cloud Function**: Automatically triggered when a file is uploaded to the GCS bucket, extracts data from the file, and loads it into BigQuery.
4. **ETL Process**: Extract, Transform, Load process implemented to handle data from raw upload to processed state.
5. **Reporting**: Summary views and dashboards in Looker Studio for key metrics, with filtering and drill-down capabilities.

## Workflow Overview
Web Interface:

A simple HTML form (index.html) enables users to upload files.
File Upload Handling:

The uploaded file is processed by Flask and saved into a specified GCS bucket (bkt-sales-data) using the Google Cloud Storage Python Client.
Storage in GCS:

The uploaded file is stored in the GCS bucket with its original filename.

## Google Cloud Storage Bucket:

A GCS bucket named bkt-sales-data must be created.
The service account must have appropriate permissions (e.g., Storage Object Admin) for this bucket.
Flask Installation:

## Install Flask and the GCS library using:
'''
    bash
    pip install flask google-cloud-storage
'''
## Service Account Key:

Ensure the service account key file is configured for authentication:
''
    bash
    Copy code
    export GOOGLE_APPLICATION_CREDENTIALS="path/to/service-account.json"
    HTML Template (templates/index.html):
'''
'''
html

    <!doctype html>
    <html>
    <head>
        <title>File Upload</title>
    </head>
    <body>
        <h1>Upload a File</h1>
        <form method="post" enctype="multipart/form-data">
            <input type="file" name="file">
            <input type="submit" value="Upload">
        </form>
    </body>
    </html>
'''
