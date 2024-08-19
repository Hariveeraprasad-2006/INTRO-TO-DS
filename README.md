# INTRO-TO-DS
# 19AI403 ASSIGNMENT-LAB INTRODUCTION
### Prepared By :Arikatla Hari Veera Prasad
### Register Number : 212223240014
### DEPT : AIML 2nd YEAR

## Requirements :

- Python 3.x
- Pandas library


## Data :

The data used for this assignment is from `bank_train.csv`, which includes various columns related to client information and their interactions with the bank.

## CODE :

## Activity 1

This section covers the tasks in Activity 1, which involve selecting specific columns and filtering rows based on certain conditions from a DataFrame.

### Task 1: Select the 'name' and 'score' columns from a given DataFrame

```python
import pandas as pd
import numpy as np

# Sample DataFrame
exam_data = {
    'name': ['Anastasia', 'Dima', 'Katherine', 'James', 'Emily', 'Michael', 'Matthew', 'Laura', 'Kevin', 'Jonas'],
    'score': [12.5, 9, 16.5, np.nan, 9, 20, 14.5, np.nan, 8, 19],
    'attempts': [1, 3, 4, 3, 5, 3, 6, 1, 7, 1]
}

df_exam = pd.DataFrame(exam_data)

# Selecting 'name' and 'score' columns
name_score_df = df_exam[['name', 'score']]
print(name_score_df)
```

**Output:**
![image](https://github.com/user-attachments/assets/25638365-6e8d-45c2-81ee-34ebb8670c2d)


### Task 2: Select the rows where the 'attempts' column is greater than 3

```python
attempts_gt_3 = df_exam[df_exam['attempts'] > 3]
print(attempts_gt_3)
```

**Output:**

![image](https://github.com/user-attachments/assets/a6c1017e-18ac-479d-97d3-6bc29725686f)


### Task 3: Index rows and columns based on specific conditions

Given DataFrame:

```python
data = {
    'name': ['Alice', 'Bob', 'Charlie', 'Dave'],
    'age': [25, 35, 40, 28],
    'gender': ['F', 'M', 'M', 'M'],
    'salary': [50000, 70000, 60000, 80000]
}
df = pd.DataFrame(data)
```

#### a. Select rows where age is greater than 30:

```python
age_gt_30 = df[df['age'] > 30]
print(age_gt_30)
```

**Output:**

![image](https://github.com/user-attachments/assets/691660ba-abc3-4189-b572-b1ae638e8842)


#### b. Select rows where name contains 'e':

```python
name_contains_e = df[df['name'].str.contains('e')]
print(name_contains_e)
```

**Output:**

![image](https://github.com/user-attachments/assets/bff12353-de16-439d-8a88-d68dc48a254f)


#### c. Select rows where gender is 'M' and salary is greater than 65000:

```python
male_high_salary = df[(df['gender'] == 'M') & (df['salary'] > 65000)]
print(male_high_salary)
```

**Output:**
![image](https://github.com/user-attachments/assets/faaa3518-965c-4859-9a20-8e5103966fc7)



#### d. Select columns 'name' and 'age':

```python
name_age_df = df[['name', 'age']]
print(name_age_df)
```

**Output:**

![image](https://github.com/user-attachments/assets/96d26fc9-7a78-4b45-9cc1-f844238b91a4)

## Activity 2

This section covers the tasks in Activity 2, which involve filtering and selecting specific rows and columns from the `bank_train.csv` dataset.

### Task a

**Condition:** Select the rows where clients with primary education have subscribed to a deposit.

```python
primary_education_subscribed = df_bank.loc[(df_bank['education'] == 'primary') & (df_bank['deposit'] == 'yes')]
print(primary_education_subscribed)
```

**Output:**

![image](https://github.com/user-attachments/assets/b3776ef5-89b4-4147-8b7b-3df81e79ca53)


### Task b

**Condition:** Select the rows where clients have not subscribed to a deposit.

```python
not_subscribed = df_bank.loc[df_bank['deposit'] == 'no']
print(not_subscribed)
```

**Output:**

![image](https://github.com/user-attachments/assets/5ad153c4-b7f3-433b-955a-1551f94ecb3c)

### Task c

**Condition:** Select the rows where clients who have subscribed to a deposit either have a housing or a personal loan.

```python
subscribed_with_loans = df_bank.loc[(df_bank['deposit'] == 'yes') & ((df_bank['housing'] == 'yes') | (df_bank['loan'] == 'yes'))]
print(subscribed_with_loans)
```

**Output:**

![image](https://github.com/user-attachments/assets/d5848067-7ef8-456c-84c2-cd0252379ae9)


### Task d

**Condition:** Select the rows where clients with secondary education who have not subscribed to a deposit.

```python
secondary_not_subscribed = df_bank.loc[(df_bank['education'] == 'secondary') & (df_bank['deposit'] == 'no')]
print(secondary_not_subscribed)
```

**Output:**

![image](https://github.com/user-attachments/assets/58ee7fa9-d8ce-470f-85c5-93115113aa58)


### Task e

**Condition:** Select the rows where clients who have subscribed to a term deposit as an outcome of the successful marketing campaign.

```python
subscribed_success = df_bank.loc[(df_bank['deposit'] == 'yes') & (df_bank['poutcome

'] == 'success')]
print(subscribed_success)
```

**Output:**

![image](https://github.com/user-attachments/assets/57dd56da-5f94-4e2d-9b2f-5f1c044a2af9)


### Task f

**Condition:** Select the rows where unemployed clients have not subscribed to a deposit.

```python
unemployed_not_subscribed = df_bank.loc[(df_bank['job'] == 'unemployed') & (df_bank['deposit'] == 'no')]
print(unemployed_not_subscribed)
```

**Output:**

![image](https://github.com/user-attachments/assets/c5e1e307-59b5-4573-8832-b5c7ba899ade)

### Task g

**Condition:** Select columns 'name' and 'salary' where age is less than or equal to 30. (Note: Adjust 'name' and 'salary' to the actual column names.)

```python
young_clients = df_bank.loc[df_bank['age'] <= 30, ['job', 'balance']]
print(young_clients)
```

**Output:**

![image](https://github.com/user-attachments/assets/770ac75d-8235-473a-a5b1-eda5e8295c8c)


## Results

The results above demonstrate how to filter and select data using Pandas' `loc` method based on specific conditions. This can be useful in analyzing marketing data and understanding client behavior.

---
