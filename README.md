# NO2-PDF-Estimation
Roll-number-based nonlinear transformation and MLE-based probability density estimation on NO2 air quality data.

# Learning Probability Density Functions using a Roll-Number-Parameterized Model

## Overview
This project demonstrates how probability density functions (PDFs) can be learned from real-world data using a roll-number-based non-linear transformation. The task is carried out on NO₂ (Nitrogen Dioxide) air quality data, followed by parameter estimation using Maximum Likelihood Estimation (MLE).

The objective is to understand how transformations affect data distributions and how statistical techniques can be used to model them effectively.

---

## Dataset Information
- Dataset: India Air Quality Dataset  
- Source: Kaggle  
- Feature Used: NO₂ concentration  
- Dataset Size: Approximately 435,000 records  

### Preprocessing Steps
- Only the NO₂ column is selected for analysis  
- Missing values are removed  
- No additional filtering or normalization is applied  

---

## Methodology

The methodology strictly follows the steps defined in the assignment.

---

### Step 1: Roll-Number-Based Non-Linear Transformation

Each NO₂ value \( x \) is transformed into a new variable \( z \) using the following equation:

\[
z = x + a_r \sin(b_r x)
\]

where:

\[
a_r = 0.05 \times (r \bmod 7)
\]

\[
b_r = 0.3 \times (r \bmod 5 + 1)
\]

Here, \( r \) represents the university roll number. This step ensures that each student works with a roll-number-specific transformation.

---

### Step 2: Probability Density Function Modeling

The transformed variable \( z \) is modeled using the following probability density function:

\[
\hat{p}(z) = c \, e^{-\lambda (z - \mu)^2}
\]

This function resembles a Gaussian distribution, where:
- \( \mu \) represents the mean of the distribution  
- \( \lambda \) controls the spread of the distribution  
- \( c \) is a normalization constant  

---

### Step 3: Parameter Estimation using Maximum Likelihood Estimation (MLE)

To estimate the parameters \( \mu \), \( \lambda \), and \( c \), Maximum Likelihood Estimation is used.

For the given Gaussian-form density, MLE provides a closed-form optimal solution:

- Mean:
\[
\mu = \text{mean}(z)
\]

- Variance:
\[
\sigma^2 = \text{var}(z)
\]

- Lambda:
\[
\lambda = \frac{1}{2\sigma^2}
\]

- Normalization Constant:
\[
c = \sqrt{\frac{\lambda}{\pi}}
\]

MLE is chosen because it is theoretically optimal, deterministic, and widely accepted in statistical modeling.

---

## Results

### Estimated Parameters

| Parameter | Value |
|---------|-------|
| μ (Mean) | 25.813 |
| λ (Lambda) | 0.001460973 |
| c | 0.02156483 |

---

### Result Visualization

A histogram of the transformed variable \( z \) is plotted to represent the empirical distribution. The estimated probability density function is overlaid as a smooth curve.

Observation: The estimated PDF closely follows the shape of the histogram, indicating that the learned parameters provide a good fit to the transformed data.

---

## Conclusion

In this project:
- A roll-number-dependent non-linear transformation was successfully applied to NO₂ air quality data.
- The transformed data was modeled using a Gaussian-type probability density function.
- Parameters were optimally estimated using Maximum Likelihood Estimation.
- The resulting PDF closely matched the empirical distribution of the data.

This work demonstrates a structured and reproducible approach to statistical modeling using real-world data.

---

## Tools and Technologies
- Python  
- NumPy  
- Pandas  
- Matplotlib  
- Google Colab  
- GitHub  

---

## Repository Structure


