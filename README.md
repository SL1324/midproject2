# Project 2 – Air Pollution Exposure Processing (BIOS 721)

This repository contains code and data for Project 2, focusing on cleaning and summarizing air pollution measurements (CO, PM2.5, O3) from 2018–2020 at the RDU airport monitor.

## Contents

- `midproject2_shan.Rmd`: R Markdown report that reads the raw EPA CSV files, processes the data, and produces the required plots.
- `AQ_2018.csv`, `AQ_2019.csv`, `AQ_2020.csv`: Daily air quality measurements for 2018–2020.
- `midproject2_shan.docx`: Knit Word report that hides codes

## How to run

1. Open `midproject2_shan.Rproj` in RStudio.
2. Knit `midproject2_shan.Rmd` to a Word document (`.docx`).
3. The Word document contains the final report with plots and interpretation.

## Background

This project processes daily air pollution data (CO, PM2.5, O₃) from the RDU monitor for 2018–2020 to create a clean exposure dataset and explore basic seasonal patterns.

## Data Processing

For each year (2018–2020), I wrote a function clean_aq() that:
	•	Renames pollutant variables to short, syntactic names.
	•	Converts Date from character to Date using mdy().
	•	Keeps only the date and pollutant columns and removes duplicate rows.
	•	Sets any negative pollutant values to 0.
	•	Averages multiple measurements within the same day to return one row per date.

I apply this function to each yearly CSV, add a year variable, and then combine the three years into one dataset. I also create a month factor (Jan–Dec) from the date for plotting.

## Plots

1. Monthly Average CO and O3 Concentrations over 3 Years
2. Monthly Average PM2.5 by Year
