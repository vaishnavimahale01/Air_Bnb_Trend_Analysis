# Air_Bnb_Trend_Analysis
# Airbnb Data Analysis  
A comprehensive data analysis project to explore and understand key trends in Airbnb listings. The analysis focuses on pricing patterns, neighborhood popularity, room types, seasonal demand, and high-performing listings.

---

## 🎯 Project Objective  
To analyze Airbnb listings to gain insights into pricing trends, popular locations, seasonal demand, and high-rated listings using SQL for data processing and Tableau for visualization.  

---

## 🛠️ Tools Used  
- **SQL:** Data extraction, transformation, and analysis.  
- **Excel:** Data preprocessing and cleanup.  
- **Power BI** Interactive data visualization.  
- **Python (Pandas, NumPy):** Data cleaning and manipulation.  

Airbnb-Data-Analysis/
├── data/
│ └── Airbnb_Listing_Data.csv # Dataset containing Airbnb listings
├── analysis/
│ └── SQL_Queries.sql # SQL scripts used for data analysis
├── visualizations/
│ └── Tableau_Dashboard.twbx # Tableau workbook (if available)
├── README.md # Project documentation
└── .gitignore # File to exclude unnecessary files

---

## 📊 Data Description  
The dataset contains the following columns:  
- **Listing ID:** Unique identifier for each Airbnb listing  
- **Host Name:** Name of the listing host  
- **Location:** City where the listing is located  
- **Room Type:** Type of room offered (Entire Home, Private Room, Shared Room)  
- **Price:** Cost per night in USD  
- **Minimum Nights:** Minimum number of nights required for booking  
- **Availability:** Number of days available per year  
- **Number of Reviews:** Count of reviews received  
- **Rating:** Average rating from guests  
- **Last Review Date:** Most recent review date  

---

## 🚀 SQL Analysis Steps  
1. **Loading Data:**  
   - Loaded the dataset into a SQL database (PostgreSQL/MySQL).  
   
2. **Data Cleaning and Transformation:**  
   - Removed duplicate records and handled missing values.  
   - Standardized the date format and handled outliers.  

3. **Analysis Queries:**  
   - Top 5 most popular locations by the number of listings:  
     ```sql
     SELECT Location, COUNT(ListingID) AS TotalListings 
     FROM AirbnbListings 
     GROUP BY Location 
     ORDER BY TotalListings DESC 
     LIMIT 5;
     ```
   - Average price by room type and location:  
     ```sql
     SELECT RoomType, Location, AVG(Price) AS AvgPrice 
     FROM AirbnbListings 
     GROUP BY RoomType, Location;
     ```
   - Seasonal demand pattern based on availability:  
     ```sql
     SELECT Location, AVG(Availability) AS AvgAvailability 
     FROM AirbnbListings 
     GROUP BY Location;
     ```
   - Highest-rated listings with more than 50 reviews:  
     ```sql
     SELECT HostName, Location, Rating 
     FROM AirbnbListings 
     WHERE Rating >= 4.5 AND NumberOfReviews > 50 
     ORDER BY Rating DESC;
     ```
   - Pricing trend by location:  
     ```sql
     SELECT Location, Price 
     FROM AirbnbListings 
     ORDER BY Price DESC 
     LIMIT 10;
     ```
   
---

## 📈 Tableau Visualization  
- **Price Distribution:** Bar charts and maps showing average prices by location.  
- **Availability Heatmap:** Visualization of booking patterns throughout the year.  
- **Top Hosts and Popular Locations:** Interactive dashboards showcasing high-performing listings.  
- **Room Type Comparison:** Visual comparison of average prices and availability by room type.  

---

## 💡 Key Insights  
- **High-Demand Locations:** Top locations include New York, San Francisco, and Los Angeles.  
- **Room Type Preferences:** Entire homes are priced approximately 30% higher than private rooms.  
- **Seasonal Trends:** High booking rates in summer and holiday seasons.  
- **Popular Hosts:** Hosts with the most listings typically maintain higher ratings.  

---

## 🚧 Challenges and Learnings  
1. **Handling Missing Values:**  
   - Solution: Used average imputation and logical assumptions.  

2. **Query Optimization:**  
   - Solution: Created indexes on frequently queried columns to improve performance.  

3. **Data Visualization:**  
   - Solution: Kept dashboards clutter-free by highlighting only key metrics.  

4. **Data Cleaning:**  
   - Solution: Addressed inconsistent formats and ensured data standardization.  

---

## ✅ Conclusion  
The project successfully analyzed Airbnb listings, providing valuable insights into pricing, location popularity, and seasonal demand. The combination of SQL for data processing and Tableau for visualization made the analysis both efficient and insightful.  

