# 📊 Web-Traffic-Analytics-Dashboard
An interactive and dynamic Power BI dashboard that visualizes web traffic, user engagement, and conversion analytics across multiple dimensions. The report incorporates key performance indicators (KPIs), session insights, bounce behavior, and device-specific engagement trends — all structured to support high-level decision-making for digital teams and analysts.
 
# 🚀 Overview
This dashboard delivers a comprehensive analysis of web traffic patterns across three core pages: Web Traffic Overview, Engagement & Devices, and Traffic & Conversions. It visualizes session-level behaviors including bounce rate, time on page, returning sessions, device category usage, and conversion effectiveness — enabling businesses to understand their users, optimize channels, and improve site performance.

# 🔧 Features
## 📌 Dynamic KPI Tracking
- Total Page Views (e.g., 8M)
- Total Conversations (e.g., 344K)
- Conversion Rate (%)
- Avg Time Per Page (seconds)
- Bounce Rate (%)
- Returning Sessions & Engaged Users

## 🌍 Traffic & Regional Analytics
- Page Views and Conversions over time
- Country-wise conversion performance via map
- Conversation rate trends by month
- Traffic Source breakdown by conversion effectiveness

## 🧠 Engagement & Device Metrics
- Session duration by device (Mobile, Tablet, Desktop)
- Engagement Score across device categories
- Page Views matrix by Day and Device
- Device usage distribution and weekly engagement (TreeMap)
- Line chart comparing Session Duration & Quality Score across devices

## 📉 Visual Intelligence
- Custom DAX Measures for Conversion MoM Growth, Quality Score, Traffic Effectiveness, IsBounce logic, etc.
- Color-coded cards, donut charts, maps, stacked bars, tree maps, and line graphs
- Interactive slicers for page navigation and filtering
- Consistent iconography and responsive layout design

# 📁 Project Structure
## 🔄 Data Layer (Power Query)
- Cleaned and transformed raw session-level web data
- Applied filters, custom columns, and engagement logic
- Created MonthYear, Device Category, and Traffic groupings

## 📐 Model Layer (DAX Measures)
- Conversion Rate, Quality Score, Traffic Effectiveness
- Conversion_MoM_Growth, Engagement Score
- IsBounce, ReturningSessions, AvgTimePerPage

## 🎨 Visuals Layer
- KPI Cards (Conversion, Bounce, Duration, Sessions)
- Pie & Donut Charts (Device, Source)
- Line & Bar Charts (Page Views, Conversion Trends)
- TreeMap & Matrix Views (Device x Day engagement)

# 🧮 Data Model
## Dimension Tables:
- Date (with Day, Month, Year, Day Name)
- Device Type / Category
- Traffic Source
- Country / Region

## Fact Table:
- website_analytics_dataset (containing session duration, page views, bounce %, conversion, etc.)

# 🔑 Sample DAX Measures
```
Conversion Rate (%) = 
DIVIDE(SUM('website_analytics_dataset'[Conversion]), SUM('website_analytics_dataset'[Page Views])) * 100
```

```
Conversion_MoM_Growth =
VAR CurrentMonth = CALCULATE(SUM('website_analytics_dataset'[Conversion]))
VAR PreviousMonth = CALCULATE(SUM('website_analytics_dataset'[Conversion]), DATEADD('website_analytics_dataset'[Date], -1, MONTH))
RETURN DIVIDE(CurrentMonth - PreviousMonth, PreviousMonth, 0)
```

# ⚙️ Installation & Usage
## 📦 Prerequisites
- Power BI Desktop (latest version)
- Access to session-level web traffic dataset (CSV or direct source)

## 🛠️ Setup Instructions
- Clone this repository
- Open the .pbix file in Power BI Desktop
- Load and refresh the dataset
- Explore and interact with the 3 dashboard pages
- Filter by device, traffic source, or region to gain new insights

# 👨‍💻 Contributor
- Vyom Raval
- 📧 ravalvyom17@gmail.com
