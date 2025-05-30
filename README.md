# Exploratory Data Analysis (EDA)

In this project, I performed initial data exploration on the training dataset to understand missing values, distributions, and relationships between features.

### Key Steps:

1. **Import necessary libraries** such as pandas, numpy, seaborn, matplotlib for data manipulation and visualization.
2. **Load the training data** from the raw data folder.
3. **Check the working directory** to ensure file paths are correct.
4. **Investigate missing values** across important features.
5. **Create missing value indicator columns** for key features with missing data, to preserve information about missingness during modeling.

### Example code snippet:

```python
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
import os

print(f"Working directory is {os.getcwd()}")

df_train = pd.read_csv("data/raw/train.csv")

# Create missing value indicators for selected columns
missing_na_features = [
    'HomePlanet', 'CryoSleep', 'Cabin', 'Destination', 'Age', 'VIP',
    'RoomService', 'FoodCourt', 'ShoppingMall', 'Spa', 'VRDeck', 'Name'
]

for col in missing_na_features:
    df_train[f'{col}_missing'] = df_train[col].isna().astype(int)

df_train['Age_missing'].head()
