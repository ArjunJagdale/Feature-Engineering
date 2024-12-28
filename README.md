# Feature Engineering Project

This project demonstrates various data transformation techniques on a customer reviews dataset to prepare it for machine learning analysis. The transformations include handling categorical data, scaling numerical features, and processing date-time values.

## Code Explanation

1. **Importing the Dataset**:
   The dataset, `reviews.csv`, is imported into a Pandas DataFrame called `reviews`.

   ```python
   reviews = pd.read_csv('reviews.csv')
   ```

2. **Exploring the Data**:
   The first step is to inspect the dataset by printing the column names and data types.

   ```python
   print(reviews.columns)
   print(reviews.info())
   ```

3. **Transforming the `recommended` Feature**:
   The `recommended` feature is binary (True/False), so it is transformed into numerical values (1/0) using a dictionary called `binary_dict`.

   ```python
   binary_dict = {'True': 1, 'False': 0}
   reviews['recommended'] = reviews['recommended'].map(binary_dict)
   print(reviews['recommended'].value_counts())
   ```

4. **Transforming the `rating` Feature**:
   The `rating` feature is ordinal, so its text values are replaced with corresponding numerical ratings using a dictionary called `rating_dict`.

   ```python
   rating_dict = {'Loved it': 5, 'Liked it': 4, 'Was okay': 3, 'Not great': 2, 'Hated it': 1}
   reviews['rating'] = reviews['rating'].map(rating_dict)
   print(reviews['rating'].value_counts())
   ```

5. **One-Hot Encoding the `department_name` Feature**:
   The `department_name` feature is one-hot encoded using `pd.get_dummies()`, which creates new columns for each department.

   ```python
   one_hot = pd.get_dummies(reviews['department_name'])
   reviews = pd.concat([reviews, one_hot], axis=1)
   print(reviews.columns)
   ```

6. **Transforming the `review_date` Feature**:
   The `review_date` feature, originally in object format, is transformed into a date-time format using `pd.to_datetime()`.

   ```python
   reviews['review_date'] = pd.to_datetime(reviews['review_date'])
   print(reviews['review_date'].dtype)
   ```

7. **Scaling the Numerical Data**:
   Finally, the numerical features are scaled using `StandardScaler` to bring them to a common scale.

   ```python
   from sklearn.preprocessing import StandardScaler
   scaler = StandardScaler()
   numerical_features = reviews.select_dtypes(include=['float64', 'int64'])
   reviews_scaled = scaler.fit_transform(numerical_features)
   ```

## Conclusion

This project covers the essential data transformations required for machine learning tasks, including encoding categorical data, handling date-time features, and scaling numerical features. The transformed dataset is now ready for further analysis or model training.

## Requirements

To run the code, ensure you have the following libraries installed:

- pandas
- scikit-learn

You can install them using pip:

```bash
pip install pandas scikit-learn
```

