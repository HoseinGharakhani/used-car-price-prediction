Used Car Price Prediction with GPT-5

A small AI project for predicting used car prices using structured vehicle data and GPT-5.

The project compares GPT-5's estimated prices with the real prices from a used-car dataset and evaluates the prediction accuracy using standard error metrics.

Project Overview

The goal of this project is to explore how well a large language model can estimate the price of a used car from its specifications.

Each car contains information such as:

Brand

Model

Model year

Mileage

Fuel type

Engine

Transmission

Exterior color

Interior color

Accident history

Clean title

The model receives these features in a structured prompt and returns an estimated price in USD.

Dataset

The project uses the Carson-Shively/used-car-price dataset from Hugging Face.

Before evaluation, the data was cleaned and normalized:

Price values converted to integers

Mileage values converted to integers

Missing categorical values replaced with unknown

Invalid categorical values normalized

For the GPT evaluation, 200 randomly selected samples were used with a fixed random seed.

Approach

The project follows this workflow:

Used Car Dataset ↓ Data Cleaning ↓ Select 200 Samples ↓ Send Car Specifications to GPT-5 ↓ GPT Price Prediction ↓ Compare with Real Price ↓ Calculate Evaluation Metrics ↓ Visualize Results 

Evaluation

The following metrics were used:

MAE — Mean Absolute Error

Measures the average absolute difference between the predicted price and the real price.

MAPE — Mean Absolute Percentage Error

Measures the average prediction error as a percentage of the real price.

R² — R-squared

Measures how well the predictions explain the variation in the real prices.

Results

Evaluation was performed on 200 used-car samples.

MetricResultMAE$8,931.62MAPE21.32% 

The project also includes visualizations for:

Price distribution

Mileage vs. price

GPT prediction errors

Example Input

Brand: Toyota Model: Camry Year: 2020 Mileage: 45000 Fuel: Gasoline Engine: 2.5L Transmission: Automatic Exterior: White Interior: Black Accident: None reported Clean title: Yes 

GPT-5 then estimates the price of the vehicle based on these specifications.

Technologies

Python

OpenAI API

GPT-5

Hugging Face Datasets

Pandas

NumPy

Matplotlib

Scikit-learn

Jupyter Notebook

Project Structure

used-car-price/ │ ├── data/ │ ├── notebook/ │ └── used_car_price.ipynb │ ├── car_price_training.jsonl │ ├── README.md │ └── requirements.txt 

Important Note

The original project explored preparing data for fine-tuning.

However, fine-tuning was not used in the final experiment. The final evaluation uses GPT-5 with structured prompts and compares its predictions against the real prices.

The car_price_training.jsonl file is therefore a prepared training-style dataset, not a fine-tuned model dataset.

Conclusion

This project demonstrates a simple experiment in using an LLM for numerical prediction from structured data.

The main focus was not building a production-grade car pricing system, but understanding:

Data cleaning

Dataset preparation

Prompt-based prediction

API usage

Evaluation metrics

Data visualization

It is a learning project focused on applying LLM engineering concepts to a real-world dataset.