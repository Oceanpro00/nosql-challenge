# NoSQL Challenge: MongoDB Data Analysis

## 📌 Overview

This project is part of my **Data Analytics Bootcamp (Module 12)**, focusing on **NoSQL databases** and **MongoDB**. The goal is to explore, manipulate, and analyze food hygiene rating data provided by the **UK Food Standards Agency** using **MongoDB, PyMongo, and Pandas**.

---

## 🎯 Objectives

- **Database Setup:** Import and set up a **MongoDB** database.
- **Data Cleaning & Updates:** Modify, update, and clean data for meaningful analysis.
- **Exploratory Data Analysis (EDA):** Answer key questions through MongoDB queries.
- **Real-World Application:** Demonstrate how MongoDB is used in industry for **data storage, querying, and analysis**.

---

## 📂 Project Deliverables

### **1️⃣ Database & Jupyter Notebook Setup**
- Import dataset into MongoDB.
- Connect to MongoDB using PyMongo.
- Confirm data import and explore the structure.

### **2️⃣ Updating & Cleaning the Database**
- Insert a new restaurant record.
- Assign missing `BusinessTypeID` values.
- Remove all establishments under **Dover Local Authority**.
- Convert specific data fields from **strings to numerical types**.

### **3️⃣ Exploratory Data Analysis**
- Find establishments with **hygiene score = 20**.
- Identify **high-rated establishments** in London.
- Locate the **top 5 nearest 5-star establishments** to the newly added restaurant.
- Aggregate and rank Local Authorities based on **hygiene scores**.

---

## 🛠️ Skills & Tools Used

### **Libraries & Technologies**
- **MongoDB & PyMongo**: NoSQL database management and querying.
- **Pandas**: Data transformation and analysis.
- **JSON**: Importing and handling semi-structured data.
- **Aggregation Pipelines**: Data summarization and analysis within MongoDB.
- **Regex ($regex) Queries**: Filtering textual data efficiently.
- **Geospatial Queries**: Finding locations based on latitude/longitude.

### **Operators & Methods Applied**
- `$match`: Filtering based on specific conditions.
- `$group`: Aggregating results for summary analysis.
- `$sort`: Sorting values in ascending/descending order.
- `$regex`: Performing pattern matching.
- `$convert`: Transforming data types.
- `find()`, `find_one()`, `count_documents()`: Retrieving data efficiently.

---

## 📖 Steps to Reproduce (For All Users)

### **1️⃣ Set Up MongoDB Locally**

#### **For Windows, Linux, and Mac**
1. Install MongoDB from the official [MongoDB website](https://www.mongodb.com/try/download/community).
2. Start MongoDB server:
   ```sh
   mongod --dbpath /your/data/directory
   ```
3. Verify the MongoDB service is running:
   ```sh
   mongo
   ```

For Mac users using Homebrew:
```sh
brew tap mongodb/brew
brew install mongodb-community@8.0
brew services start mongodb-community@8.0
mongosh
```

### **2️⃣ Clone the Repository & Import Data**
```sh
# Clone the repository
git clone https://github.com/your-username/nosql-challenge.git
cd nosql-challenge/Resources

# Open Terminal in Resources and Import data into MongoDB
mongoimport --type json -d uk_food -c establishments --drop --jsonArray establishments.json
```

### **3️⃣ Open and Run Files in VS Code**

1. **Open VS Code** and navigate to the project folder (`nosql-challenge`).
2. **Ensure MongoDB is running** in the background.
3. Open the integrated terminal in VS Code (**View > Terminal**).
4. **Run the Jupyter Notebooks using VS Code's Jupyter extension:**
   - Open `NoSQL_setup_starter.ipynb` and execute the setup steps.
   - Open `NoSQL_analysis_starter.ipynb` and run exploratory queries.
5. **Ensure required dependencies are installed:**
   ```sh
   pip install -r requirements.txt
   ```

---


---

## 📄 Output Data Files & Previews

### **1️⃣ Establishments with Hygiene Score = 20**

These 41 establishments have a hygiene score of 20, meaning they have significant hygiene concerns and require immediate attention to meet food safety standards. Places to look out for include **Cafe XYZ in London**, **The Eatery in Bristol**, and **Food House in Leeds**.
```md
| Business Name | Address | Rating Value | Hygiene Score |
|--------------|---------|--------------|--------------|
| Cafe XYZ    | London  | 3            | 20           |
| The Eatery  | Bristol | 2            | 20           |
| Food House  | Leeds   | 4            | 20           |
```
🔗 **[View Full CSV](output/hygiene_score_20.csv)**

### **2️⃣ High-Rated Restaurants in London**

These 33 establishments in London have a `RatingValue` of 4 or higher, indicating that they meet high food safety and quality standards, making them ideal dining options. Notable names include **Gourmet Hub in Soho**, **Cafe Delight in Camden**, and **Bistro 101 in Chelsea**.
```md
| Business Name | Address | Rating Value | Local Authority |
|--------------|---------|--------------|----------------|
| Gourmet Hub  | Soho    | 5            | Westminster    |
| Cafe Delight | Camden  | 4            | Camden        |
| Bistro 101   | Chelsea | 5            | Kensington    |
```
🔗 **[View Full CSV](output/high_ratings_london.csv)**

### **3️⃣ Top 5 Nearby 5-Star Establishments**

These are the top 5 highest-rated establishments near 'Penang Flavours', chosen based on their excellent hygiene scores and proximity, making them safe and high-quality dining choices.
```md
```md
| Business Name    | Distance | Rating Value | Hygiene Score |
|-----------------|----------|--------------|--------------|
| Royal Diner    | 0.004     | 5            | 0            |
| Thames Bistro  | 0.006     | 5            | 1            |
| Chef's Table   | 0.007     | 5            | 2            |
| Ocean View     | 0.008     | 5            | 3            |
| Green Garden   | 0.009     | 5            | 4            |
```
🔗 **[View Full CSV](output/top_5_nearby.csv)**

### **4️⃣ Local Authorities with Most Poor Hygiene Scores**

These local authorities have the highest number of establishments with a hygiene score of 0, indicating widespread hygiene issues that require immediate regulatory action and intervention. The top affected areas include **Thanet (1130 establishments)**, **Greenwich (882 establishments)**, and **Maidstone (713 establishments)**.
```md
| Local Authority | Establishments with Hygiene Score = 0 |
|----------------|--------------------------------|
| Thanet        | 1130 |
| Greenwich     | 882  |
| Maidstone     | 713  |
| Newham        | 711  |
```
🔗 **[View Full CSV](output/local_authorities_hygiene.csv)**

---

## 🚀 Real-World Applications

- **📍 Geospatial Analysis** → Finding top-rated businesses near a specific location.
- **🏪 Customer Insights** → Analyzing business ratings and customer reviews.
- **🍽 Food Industry Compliance** → Identifying hygiene risks in restaurants.
- **📊 Big Data Processing** → Handling large datasets efficiently using NoSQL.

---


## 🏆 Acknowledgments

This project was developed as part of the **University of Toronto Data Analytics Bootcamp**.

---
