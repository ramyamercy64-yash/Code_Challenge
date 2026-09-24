
# Coding_Challenge_Day3

# Quality Control Dashboard(manufacturing company)– Power BI

## 📌 Project Overview

This project focuses on building an interactive **Quality Control Dashboard** using Power BI for a manufacturing company.

The objective is to monitor product defects, identify problematic products and batches, and understand how the defect rate changes over time.

## 🎯 Business Questions

The dashboard answers the following key business questions:

1. What is the overall defect rate?
2. Which products have the highest number of defects?
3. Is the defect rate improving or worsening over time?
4. Are certain inspection batches performing worse than others?

## 📊 Dataset

The project uses production and quality inspection data.

### Production Table

The Production table contains:

* ProductID
* BatchID
* Date
* Status (Pass/Fail)

### Batches Table

The Batches table contains:

* BatchID
* ProductionLine
* InspectorName

The two tables are connected using **BatchID**.

## 🛠️ Tools Used

* Power BI
* Power Query
* DAX
* CSV / Excel data

## 📐 DAX Measures

### Defective Items

```DAX
Defective Items =
CALCULATE(
    COUNTROWS(Production),
    Production[Status] = "Fail"
)
```

### Total Items

```DAX
Total Items =
COUNTROWS(Production)
```

### Overall Defect Rate

```DAX
Overall Defect Rate =
DIVIDE(
    [Defective Items],
    [Total Items],
    0
)
```

### Daily Defect Rate

```DAX
Daily Defect Rate =
DIVIDE(
    [Defective Items],
    [Total Items],
    0
)
```

## 📈 Dashboard Visualizations

### 1. Overall Defect Rate

A **Card visual** is used to prominently display the overall defect rate.

### 2. Top 5 Products by Defects

A **Clustered Bar Chart** displays the five products with the highest number of defects.

### 3. Defect Rate Trend

A **Line Chart** displays the daily defect rate over time to help identify whether the defect rate is improving or worsening.

### 4. Defects by Production Batch

A **Matrix/Table** is used to analyze defect counts by:

* BatchID
* ProductionLine
* InspectorName

### 5. Date Filter

A **Date Slicer** allows users to filter the dashboard for a specific time period.

These visualizations follow the requirements specified in the Quality Control Dashboard task.

## 📁 Project Structure

```text
Quality-Control-Dashboard/
│
├── Dataset/
│   ├── Production.csv
│   └── batches_data.csv
│
├── PowerBI/
│   └── Quality_Control_Dashboard.pbix
│
├── Images/
│   └── Dashboard_Screenshot.png
│
└── README.md
```

## 💡 Key Insights

The dashboard helps management:

* Monitor the overall defect rate.
* Identify the top 5 products with the highest defects.
* Track defect-rate trends over time.
* Identify batches with higher defect counts.
* Analyze defects by production line and inspector.
* Filter the analysis by date.

## 📌 Conclusion

The Quality Control Dashboard provides an interactive view of manufacturing quality performance. It helps the production manager monitor defects, identify problematic products and batches, and track quality trends over time.


