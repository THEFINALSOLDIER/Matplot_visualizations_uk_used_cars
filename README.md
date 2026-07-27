# Matplot_visualizations_uk_used_cars
# Matlplotlib_Visualizations

## Overview

This is a data visualization project that uses **Python, Pandas, and Matplotlib** to visualize and explore a dataset containing information about used cars in the UK.

The dataset contains **3,685 rows and 12 columns** with information about car prices, mileage, registration year, previous owners, fuel type, body type, engine, gearbox, doors, seats, and emission class.

---

## Dataset

The dataset used in this project is:

`used_cars_UK.csv`

### Dataset Features

- `title` — Car model/title
- `Mileage(miles)` — Mileage of the car in miles
- `Registration_Year` — Year the car was registered
- `Previous Owners` — Number of previous owners
- `Fuel type` — Fuel type of the car
- `Body type` — Body type of the car
- `Engine` — Engine size
- `Gearbox` — Type of gearbox
- `Doors` — Number of doors
- `Seats` — Number of seats
- `Emission Class` — Emission class of the car
- `Price` — Price of the car

---

## Visualizations

The visualizations created in this project include:

- Price vs Registration Year
- Price vs Mileage
- Average Price by Previous Owners
- Average Price by Fuel Type
- Average Price by Body Type
- Average Price by Gearbox

---

> The codes in this repo can be run on any IDE of choice or in Google Colab.

---

## Python Codes

### Importing the Libraries and Loading the Dataset

```python
import pandas as pd
import matplotlib.pyplot as plt

# Loading the dataset
df = pd.read_csv("used_cars_UK.csv")

# Display the first 10 rows
df.head(10)
```
---

## Price vs Registration Year

```python
plt.figure(figsize=(8, 5))

plt.scatter(
    df["Registration_Year"],
    df["Price"],
    alpha=0.5
)

plt.title("Car Price vs Registration Year")
plt.xlabel("Registration Year")
plt.ylabel("Price")

plt.show()
```
<img width="1280" height="800" alt="WhatsApp Image 2026-07-27 at 6 46 50 PM (4)" src="https://github.com/user-attachments/assets/59b2a335-9c56-4f6f-8376-bc7a0cd22b0d" />
---

## Price vs Mileage

```python
plt.figure(figsize=(8, 5))

plt.scatter(
    df["Mileage(miles)"],
    df["Price"],
    alpha=0.5
)

plt.title("Car Price vs Mileage")
plt.xlabel("Mileage (miles)")
plt.ylabel("Price")

plt.show()
```
<img width="1280" height="800" alt="WhatsApp Image 2026-07-27 at 6 46 50 PM (2)" src="https://github.com/user-attachments/assets/879b3f00-00f3-4f56-ac89-84186fcfa1d1" />
---

## Average Car Price by Previous Owners

```python
# Calculate average price by number of previous owners
owner_price = df.groupby("Previous Owners")["Price"].mean().sort_values()

# Create bar chart
plt.figure(figsize=(8, 5))

plt.bar(
    owner_price.index.astype(str),
    owner_price.values
)

plt.title("Average Car Price by Previous Owners")
plt.xlabel("Number of Previous Owners")
plt.ylabel("Average Price")

plt.show()
```
<img width="1280" height="800" alt="WhatsApp Image 2026-07-27 at 6 46 50 PM (1)" src="https://github.com/user-attachments/assets/054e2acd-f616-4bd9-a854-12fe6995b716" />
---

## Average Car Price by Fuel Type

```python
# Calculate average price for each fuel type
fuel_price = df.groupby("Fuel type")["Price"].mean().sort_values()

# Create bar chart
plt.figure(figsize=(8, 5))

plt.bar(
    fuel_price.index,
    fuel_price.values
)

plt.title("Average Car Price by Fuel Type")
plt.xlabel("Fuel Type")
plt.ylabel("Average Price")

plt.xticks(rotation=45)

plt.show()
```
<img width="1280" height="800" alt="WhatsApp Image 2026-07-27 at 6 46 50 PM (3)" src="https://github.com/user-attachments/assets/901e1177-c81a-4a99-9369-a90adf997852" />

---

## Average Car Price by Body Type

```python
# Calculate average price for each body type
body_price = df.groupby("Body type")["Price"].mean().sort_values()

# Create bar chart
plt.figure(figsize=(8, 5))

plt.bar(
    body_price.index,
    body_price.values
)

plt.title("Average Car Price by Body Type")
plt.xlabel("Body Type")
plt.ylabel("Average Price")

plt.xticks(rotation=45)

plt.show()
```
<img width="1280" height="800" alt="WhatsApp Image 2026-07-27 at 6 46 50 PM" src="https://github.com/user-attachments/assets/17ef31dc-4b32-4935-a940-46822e67b8eb" />
---

## Average Car Price by Gearbox

```python
# Calculate average price for each gearbox type
gearbox_price = df.groupby("Gearbox")["Price"].mean().sort_values()

# Create bar chart
plt.figure(figsize=(8, 5))

plt.bar(
    gearbox_price.index,
    gearbox_price.values
)

plt.title("Average Car Price by Gearbox")
plt.xlabel("Gearbox")
plt.ylabel("Average Price")

plt.show()
```
<img width="1280" height="800" alt="WhatsApp Image 2026-07-27 at 6 46 49 PM" src="https://github.com/user-attachments/assets/f2a4222e-c607-4170-8367-55781576e0e3" />
---

