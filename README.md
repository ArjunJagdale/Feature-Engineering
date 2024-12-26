Here's a neatly formatted version for your README.md file:

# **Transforming Data into Features**

You are a data scientist at a clothing company and are working with a dataset of customer reviews. This dataset is originally from [Kaggle](https://www.kaggle.com/nicapotato/womens-ecommerce-clothing-reviews) and has a lot of potential for various machine learning purposes. You are tasked with transforming some of these features to make the data more useful for analysis. To do this, you will have time to practice the following:

- Transforming categorical data
- Scaling your data
- Working with date-time features

## **Basic Exploration**

1. Let’s start with some basic exploring by performing the following:

   - First, import your dataset. It is stored under a file named `reviews.csv`. Save it to a variable called `reviews`.
   - Next, we want to look at the column names of our dataset along with their data types. Do the following two steps:
     - Print the column names of your dataset.
     - Check your features’ data types by printing `.info()`.

## **Data Transformations**

1. Transform the `recommended` feature. Start by printing the feature’s `.value_counts()`.

2. Since this is a True/False feature, we want to transform it to 1 for True and 0 for False.

   - To do this, create a dictionary called `binary_dict` where:
     - The keys are what is currently in the `recommended` feature.
     - The values are what we want in the new column (0s and 1s).

3. Using `binary_dict`, transform the `recommended` column so that it will now be binary. Print the results using `.value_counts()` to confirm the transformation.

4. Let’s run through a similar process to transform the `rating` feature. This is ordinal data, so our transformation should make that more clear. Again, start by printing the `.value_counts()`.

   - We want to make the following changes to the values:
     - ‘Loved it’ → 5
     - ‘Liked it’ → 4
     - ‘Was okay’ → 3
     - ‘Not great’ → 2
     - ‘Hated it’ → 1

   - Create a dictionary called `rating_dict` where the keys are what is currently in the feature and the values are what we want in the new column. You can use the hierarchy listed above to make your dictionary.

5. Using `rating_dict`, transform the `rating` column so it contains numerical values. Print the results using `.value_counts()` to confirm the transformation.

6. Let’s now transform the `department_name` feature. This process will be slightly different, but start by printing the `.value_counts()` of the feature.

   - Use Panda’s `get_dummies` to one-hot encode our feature.
   - Attach the results back to our original data frame.
   - Print the column names to see!

7. Use Panda’s `get_dummies()` method to one-hot encode our feature. Assign this to a variable called `one_hot`.

8. Join the results from `one_hot` back to our original data frame. Then print out the column names. What has been added?

9. Let’s make one more feature transformation! Transform the `review_date` feature.

   - This feature is listed as an `object` type, but we want this to be transformed into a date-time feature.
   - Transform `review_date` into a date-time feature.
   - Print the feature type to confirm the transformation.

## **Scaling the Data**

1. The final step we will take in our transformation project is scaling our data. We notice that we have a wide range of numbers thus far, so it is best to put everything on the same scale.

   - Let’s get our data frame to only have the numerical features we created.
   - Reset the index to be our `clothing_id` feature.

2. We are ready to scale our data! Perform a `.fit_transform()` on our dataset, and print the results to see how the features have changed.

3. Congratulations! You have successfully completed this transformation project. Transformations are an incredibly valuable skill to have. Great job!
