# Transforming-health-care--AIData Description :

import pandas as pd

data = pd.read_csv('patient_data.csv')
print(data.head())

Data Preprocessing:

from sklearn.preprocessing import LabelEncoder

# Handling categorical variables
data['Gender'] = LabelEncoder().fit_transform(data['Gender'])

# Handling missing values
data.fillna(data.mean(), inplace=True)

print(data.isnull().sum())

Exploratory Data Analysis (EDA):

import seaborn as sns
import matplotlib.pyplot as plt

sns.countplot(x='Disease', data=data)
plt.title('Disease Distribution')
plt.show()

Visualization of Results & Model Insights:

from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score

# Splitting the data
X = processed_data.drop('disease', axis=1)
y = processed_data['disease']
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Model building
model = RandomForestClassifier(n_estimators=100, random_state=42)
model.fit(X_train, y_train)

# Predicting
y_pred = model.predict(X_test)

# Model evaluation
accuracy = accuracy_score(y_test, y_pred)
print(f'Accuracy: {accuracy * 100:.2f}%').
