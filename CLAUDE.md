# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a machine learning project for house price prediction using the Ames Housing dataset. The project is implemented as a Jupyter notebook (`estudo-dirigido.ipynb`) that uses TensorFlow Decision Forests for regression analysis.

## Development Environment

- **Python**: 3.10.12
- **Primary Framework**: TensorFlow 2.19.0 with TensorFlow Decision Forests 1.12.0
- **Data Processing**: Pandas 2.3.2
- **Visualization**: Matplotlib 3.10.5, Seaborn 0.13.2
- **Environment**: Jupyter notebook with Kernel execution support

## Running the Project

Since this is a Jupyter notebook project, execute cells sequentially in `estudo-dirigido.ipynb`. The notebook contains:

1. **Data Loading and Exploration**: Loads training data from `./files/train.csv`
2. **Data Analysis**: Statistical analysis and visualization of housing features
3. **Model Training**: Uses Random Forest from TensorFlow Decision Forests
4. **Prediction**: Generates predictions on test data and saves to `./files/submission.csv`

## Dataset Structure

The housing dataset contains 80 features describing residential properties in Ames, Iowa:

- **Target Variable**: `SalePrice` (house sale price)
- **Feature Types**: Mix of numerical (37 features) and categorical (43 features)
- **Key Features**: Neighborhood, GrLivArea, TotalBsmtSF, GarageArea, OverallQual
- **Data Files**:
  - `./files/train.csv`: Training dataset (1460 samples)
  - `./files/test.csv`: Test dataset for predictions
  - `./files/data_description.txt`: Detailed feature descriptions
  - `./files/submission.csv`: Generated predictions output

## Model Architecture

The project uses TensorFlow Decision Forests with:

- **Algorithm**: Random Forest regression
- **Data Split**: 70% training, 30% validation (manual split using numpy.random)
- **Data Format**: Pandas DataFrame converted to TensorFlow Dataset
- **Feature Importance**: Multiple metrics available (INV_MEAN_MIN_DEPTH, NUM_AS_ROOT, SUM_SCORE, NUM_NODES)

## Key Implementation Details

- **Missing Data**: Dataset contains significant missing values in features like Alley (91/1460), PoolQC (7/1460), MiscFeature (54/1460)
- **Feature Engineering**: No explicit feature engineering; relies on Decision Forest's ability to handle mixed data types
- **Visualization**: Custom plotting functions for variable importance analysis
- **Output**: Predictions saved in competition submission format

## File Dependencies

When modifying the notebook, ensure these file paths remain valid:
- Training data: `"./files/train.csv"`
- Test data: `"./files/test.csv"`
- Submission output: `"./files/submission.csv"`