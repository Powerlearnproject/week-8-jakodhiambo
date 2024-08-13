# Solving an SDG Problem with Data (Choose Your SDG)

## Overview
Select a Sustainable Development Goal (SDG) that resonates with you and develop a data-driven solution to address a specific problem within that SDG. Design a database, perform data analysis, and use Microsoft Excel as the user interface.

## Objectives
- Choose an SDG and identify a specific problem to address.
- Design and implement a relational database relevant to your chosen problem.
- Write SQL queries to retrieve and analyze data.
- Use Microsoft Excel for data visualization and analysis.

## Requirements

### Part 1: SDG Selection and Problem Definition
- **SDG Selection:** Choose an SDG (e.g., SDG 3: Good Health, SDG 7: Affordable and Clean Energy).
- **Problem Definition:** Define a specific problem within your chosen SDG that can be addressed using data.

- SDG Selection: Choose an SDG that resonates with you. For example, SDG 6: Clean Water and Sanitation.
Problem Definition: Identify a specific issue within the chosen SDG. For SDG 6, a potential problem could be "Lack of access to clean drinking water in rural areas."

### Part 2: Database Design
- **ERD:** Design an ERD for your project, including entities relevant to your SDG problem.
- **Schema:** Write SQL statements to create the database schema based on your ERD.
- **Sample Data:** Populate the database with relevant sample data.

- ERD:

Entities: Water Sources, Rural Areas, Water Quality Reports, Access Points.
Relationships:
Rural Areas are served by multiple Water Sources.
Water Quality Reports are linked to Water Sources.
Access Points provide data on availability and accessibility.
Schema:

CREATE TABLE WaterSources (
    SourceID INT PRIMARY KEY,
    SourceName VARCHAR(255),
    SourceType VARCHAR(255),
    Location VARCHAR(255)
);

CREATE TABLE RuralAreas (
    AreaID INT PRIMARY KEY,
    AreaName VARCHAR(255),
    Population INT
);

CREATE TABLE WaterQualityReports (
    ReportID INT PRIMARY KEY,
    SourceID INT,
    ReportDate DATE,
    QualityIndex DECIMAL(5,2),
    FOREIGN KEY (SourceID) REFERENCES WaterSources(SourceID)
);

CREATE TABLE AccessPoints (
    AccessID INT PRIMARY KEY,
    AreaID INT,
    SourceID INT,
    AccessibilityScore DECIMAL(5,2),
    FOREIGN KEY (AreaID) REFERENCES RuralAreas(AreaID),
    FOREIGN KEY (SourceID) REFERENCES WaterSources(SourceID)
);
Sample Data:

Populate tables with fictional data representing water sources, rural areas, quality reports, and access points.

### Part 3: SQL Programming
- **Data Retrieval:** Write SQL queries to retrieve relevant data based on your problem definition.
- **Data Analysis:** Write SQL queries to analyze data and generate insights related to your SDG problem.

Data Retrieval:

SELECT * FROM WaterSources;
SELECT * FROM RuralAreas;
Data Analysis:

-- Average quality index of water sources
SELECT AVG(QualityIndex) AS AvgQuality FROM WaterQualityReports;

-- Access score for each rural area
SELECT AreaName, AVG(AccessibilityScore) AS AvgAccessScore
FROM AccessPoints
JOIN RuralAreas ON AccessPoints.AreaID = RuralAreas.AreaID
GROUP BY AreaName;
### Part 4: Data Analysis Using Excel
- **Import Data:** Import data from your database into Excel.
- **Analysis:** Analyze the data using pivot tables, charts, and other Excel tools.
- **Dashboard:** Create an interactive Excel dashboard to visualize key insights.

- Import Data: Use Excel’s data import feature to bring data from the database.
Analysis:
Create Pivot Tables to summarize data.
Generate charts such as bar charts for average water quality and line charts for accessibility trends.
Dashboard:
Use Excel’s dashboard features to create interactive visualizations.
Include slicers for filtering by area or date.

### Part 5: Integration and Testing
- **Integration:** Document the process of importing data into Excel and ensuring consistency.
- **Testing:** Test the integration and functionality of your Excel dashboard.

Integration:
Document the process for importing data into Excel.
Ensure data consistency between the database and Excel.
Testing:
Test the dashboard functionality and data accuracy.
### Part 6: Presentation
- **Pitch Deck:** Develop a 10-slide PowerPoint presentation as taught in the entrepreneurship module covering:
  - Project overview and SDG alignment.
  - Problem definition and significance.
  - Database design and schema.
  - Data analysis insights.
  - Excel dashboard demonstration.
- **Delivery:** Present your pitch deck, demonstrating how your project addresses the SDG problem.

- Pitch Deck:

Slide 1: Project Overview and SDG Alignment
Slide 2: Problem Definition and Significance
Slide 3: Database Design and Schema
Slide 4: Data Analysis Insights
Slide 5: Excel Dashboard Demonstration
Slides 6-10: Additional insights, future steps, and Q&A
Delivery:

Prepare to present the pitch deck, highlighting the problem, data-driven solution, and key insights from your dashboard.

## Deliverables
- SDG problem definition document
- ERD
- SQL scripts
- Excel workbook with data analysis and dashboard
- Integration documentation
- Pitch deck presentation
