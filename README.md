# Amazon_finals
OCR and Entity Extraction from Images

Contested in Amazon's yearly ML hackathon challenge and stood amongst top 100 teams in the finals amongst total participation of 75000 teams
OCR and Entity Extraction from Images
Overview
This script is designed to process images from a dataset, extract textual content using Optical Character Recognition (OCR) via the easyocr library, and identify specific entity types such as dimensions, weight, and volume. It uses regex-based extraction to identify and standardize units of measurement from the OCR results.

Prerequisites
Python 3.x
Libraries:
pandas for dataset manipulation.
easyocr for performing OCR on images.
requests to fetch images from URLs.
Pillow (PIL) for image handling.
re for regex operations.

Usage
Dataset: Prepare your dataset in CSV format with columns image_link, entity_name(weight, dimensions, height, width and etc.) and group_id.
Modify Script: Update the csv_file_path variable with the path to your CSV file.
Run the Script: Execute the script to process the images and extract the desired entities.
Results: The script outputs a new CSV file named processed_results.csv containing the image URLs and extracted entity value of any product.

Script Breakdown
Data Loading: Loads the image URLs and entity specifications from a CSV file.
OCR Setup: Initializes an OCR reader which is configured to recognize English text.
Entity Extraction: Uses regex patterns to identify and convert units of measurement within the recognized text.
Unit Conversion Dictionary: A comprehensive mapping to standardize unit abbreviations to their full names.

Main Process Loop:
Fetches each image via its URL.
Applies OCR to extract text.
Uses regex to find and format the first occurrence of specified entities.
Collects all results into a dataframe and saves it to CSV.

Output
The output CSV file includes columns for image_url and entity_value, where entity_value contains the extracted information formatted as <numeric value> <unit>.
