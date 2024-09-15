# Python Data Preprocessing and Element-wise Operations
## Description
This project includes solutions for two data preprocessing tasks using Python and NumPy. The tasks involve:
1. Normalizing a random 5x5 NumPy ndarray.
2. Performing element-wise operations on a 10x10 ndarray of squared integers to find numbers divisible by 3.

## Tasks

### 1. **Normalization Problem:**
   Normalization is a key preprocessing technique in data analytics, used to center and scale data for various applications. In this project, normalization is performed by subtracting the mean of the data from each element and dividing by the standard deviation. The formula is given as:

  ![image](https://github.com/user-attachments/assets/f49bc35d-4e95-4294-9cd2-700f83802127)


   - A random 5x5 NumPy ndarray is created.
   - The ndarray is normalized using the mean and standard deviation of its elements.
   - The normalized array is saved as `X_normalized.npy`.
*Input:*

```python

# Import necessary library
import numpy as np

#  Create a random 5x5 ndarray and store it in variable X
X = np.random.rand(5, 5)  # Creates a 5x5 array with random values between 0 and 1

# Step 2: Calculate the mean and standard deviation of the array
mean = X.mean()
std_dev = X.std()

# Step 3: Normalize X using the Z-score formula
X_normalized = (X - mean) / std_dev

# Step 4: Save the normalized array as X_normalized.npy
np.save('X_normalized.npy', X_normalized)

# Display the original and normalized arrays
print("Original Array:\n", X)
print("\nNormalized Array:\n", X_normalized)
```
*Output:*

![image](https://github.com/user-attachments/assets/332e081c-9dfe-4016-9e23-631ddbca1f59)

*to verify the saved array*
```phython
np.save('X_normalized.npy', X_normalized)
```
*Output:*
![image](https://github.com/user-attachments/assets/030f5fb6-a821-4111-8450-3724510d9d02)

### 2. **Divisible by 3 Problem:**
   A 10x10 NumPy ndarray is created where each element represents the square of the first 100 positive integers. The goal is to:
   - Identify all elements that are divisible by 3.
   - Save the resulting elements into a file named `div_by_3.npy`.

 *Input:*
```phython
# Import necessary library
import numpy as np
# Step 1: Create an array of the first 100 positive integers and square them
numbers = np.arange(1, 101)  # Array of integers from 1 to 100
squares = numbers ** 2       # Square each element
# Step 2: Reshape the array into a 10x10 ndarray
A = squares.reshape(10, 10)
# Step 3: Find all elements in the array that are divisible by 3
divisible_by_3 = A[A % 3 == 0]
# Step 4: Save the result as div_by_3.npy
np.save('div_by_3.npy', divisible_by_3)
# Display the original array and elements divisible by 3
print("10x10 Array of Squares:\n", A)
print("\nElements Divisible by 3:\n", divisible_by_3)
```
*Output:*
![image](https://github.com/user-attachments/assets/bff9fb1f-fd65-4294-afa0-c6879c13ee21)


*to verify the saved array*
```phython
np.save('div_by_3.npy', divisible_by_3)
```
