# ⚽ FIFA World Cup Analytics (1930–2026)

<p align="center">
  <strong>🌍 Explore Football History. 📊 Discover Trends. 🏆 Celebrate Champions.</strong>
</p>

An interactive Microsoft Power BI dashboard exploring FIFA World Cup history, championship records, goals and attendance trends, and the 2026 tournament schedule. This project transforms football data into meaningful insights through interactive visualizations, KPI cards, and dynamic filters.

---

## 📸 Dashboard Preview

<p align="center">
  <img src="https://github.com/shubham-2359/fifa-world-cup-analytics-powerbi-dashboard/blob/master/assets/fifa-world-cup-dashboard.png" alt="FIFA World Cup Analytics Power BI Dashboard" width="100%"/>
</p>

<p align="center">
  <em>From legendary champions to the 2026 match schedule — one interactive dashboard for exploring the world's biggest football tournament.</em>
</p>

---

## 📑 Table of Contents

- [🎯 Project Objective](#-project-objective)
- [💼 Business Problems](#-business-problems)
- [🗂️ Dataset Overview](#️-dataset-overview)
- [🛠️ Tools & Technologies](#️-tools--technologies)
- [⚙️ Project Workflow](#️-project-workflow)
  - [🧹 Data Cleaning & Transformation](#-data-cleaning-&-transformation)
  - [🔗 Tournament Stage Sorting & Data Modeling](#-tournament-stage-sorting-&-data-modeling)
  - [🧮 DAX Measures](#-dax-measures)
  - [🎛️ Dashboard Filters](#️-dashboard-filters)
  - [📊 Dashboard Visualizations](#-dashboard-visualizations)
- [🔍 Key Insights](#-key-insights)
- [💡 Business Recommendations](#-business-recommendations)
- [🔮 Future Scope](#-future-scope)
- [🤝 Author](#-author)
- [⚖️ Disclaimer](#️-disclaimer)

---

## 🎯 Project Objective

The primary objective of this project is to build an interactive Power BI dashboard combining historical FIFA World Cup records from 1930 to 2026 with the 2026 match schedule.

**What this dashboard delivers**

- 🏆 Analyzes championship records across nations.
- ⚽ Explores historical goals and attendance trends.
- 🌍 Compares host-country attendance patterns.
- 📅 Examines the distribution of 2026 matches across tournament stages and dates.
- 🏟️ Analyzes scheduled match allocation across stadiums.
- 🎛️ Enables interactive exploration through six dashboard slicers.

**Goal:** Turn football data into clear, accessible, and actionable analytical insights.

---

## 💼 Business Problems

FIFA World Cup information is spread across historical tournament records, championship statistics, attendance data, host-country information, and match schedules.<br> Analyzing these separately can make it difficult to identify long-term trends, compare editions, and understand how matches are distributed across venues and tournament stages.

This dashboard brings these datasets together to support a more structured and interactive analysis.

### 🔍 Business Questions Answered

| Business Question | Dashboard Solution |
|---|---|
| 🏆 Which nations have won the most World Cup titles? | Championship ranking bar chart |
| ⚽ How have goals changed across tournament editions? | Historical goals trend |
| 👥 How has average attendance changed over time? | Goals and attendance trend visual |
| 🌍 How does attendance vary across host nations? | Geographic map and attendance table |
| 📊 What proportion of 2026 matches belongs to each stage? | Stage distribution doughnut chart |
| 📅 How are matches distributed across tournament dates? | 2026 match timeline |
| 🏟️ Which stadiums have the most scheduled matches? | Stadium treemap |

The dashboard supports historical comparison and schedule exploration. Additional analysis is required to explain the causes behind observed changes.

---

## 🗂️ Dataset Overview

The project uses a self-prepared Excel workbook containing two worksheets.

### 📚 Dataset 1: Historical Win

A historical summary of FIFA World Cup editions represented in the dataset from 1930 to 2026.

**Key attributes include:**

- 📅 Tournament year and dates
- 🌍 Host country
- 🏆 Champion and runner-up
- 🥉 Third-place and fourth-place teams
- 👥 Participating teams and attendance figures
- ⚽ Total goals and matches
- 🎯 Top scorer information

**Analytical purpose:** Supports historical KPIs, championship rankings, and goals and attendance trend analysis.

### 🗓️ Dataset 2: FIFA World Cup 2026 Match Schedule

A match-schedule dataset containing 104 match records for the 2026 tournament.

**Key attributes include:**

- 🆔 Match ID
- 🏟️ Stadium and host city
- 🌍 Host country
- 📅 Match date
- 🕒 Kickoff time in Pacific Time and Eastern Time
- ⚽ Participating teams or fixture labels
- 🏆 Tournament stage
- 🌐 Team confederations
- 🔢 Knockout-stage indicator

**Analytical purpose:** Supports the match timeline, stage distribution, stadium allocation, and host-country analysis.

### 🔎 Data Collection & Preparation

I independently researched, collected, and structured this dataset using FIFA's official World Cup resources and other publicly available websites. AI tools were used as an aid during the research and data preparation process.

The collected information was organized into two worksheets and prepared for analysis in Power BI.

**Data-quality considerations:**

- Historical country names may differ from modern country names.
- The 2026 schedule represents fixtures and should not automatically be interpreted as completed matches.
- Historical summary figures for the 2026 edition should be verified against final official records.

This is an independently compiled analytical dataset, not a dataset supplied as-is by FIFA.

---

## 🛠️ Tools & Technologies

| Tool/Technology | Application |
|---|---|
| **🟡 Microsoft Power BI Desktop** | Dashboard development and interactive reporting |
| **🧹 Power Query Editor** | Data cleaning, transformation, and standardization |
| **🧮 DAX** | KPI measures and calculated dimension tables |
| **📗 Microsoft Excel** | Dataset storage and preparation |
| **🔗 Data Modeling** | Relationships and tournament-stage sorting |
| **📊 Data Visualization** | KPI cards, bar charts, line charts, doughnut charts, maps, tables, and treemaps |

---

## ⚙️ Project Workflow

### 🧹 1. Data Cleaning & Transformation

#### 🔹 Step 1: Data Import

1. Open Power BI Desktop.
2. Navigate to **Home → Get Data → Excel Workbook**.
3. Select the project Excel file.
4. Select both worksheets:
   - `Historical Win`
   - `FIFA World Cup 2026 Match`
5. Click **Transform Data** to open Power Query Editor.

#### 🔹 Step 2: Data Transformation & Cleaning

In Power Query Editor:

- 🔍 Inspected columns and data quality.
- 🔢 Verified numerical data types.
- 📅 Checked date and time fields.
- 📝 Reviewed text columns for inconsistent values.
- ⚠️ Identified missing values and potential errors.
- 🧹 Corrected data types and inconsistencies where necessary.

#### 🔹 Step 3: Standardize Champion Country Names

To support modern country-level comparisons:

1. Selected the `Champion` column in `Historical Win`.
2. Duplicated the column.
3. Renamed the duplicate to `Champion Current Country`.
4. Replaced `West Germany` with `Germany` in the duplicated column.
5. Preserved the original `Champion` column.
6. Verified the updated values and data type.

This allows selected analyses to use standardized country labels without overwriting the original historical information.

#### 🔹 Step 4: Apply Changes

After reviewing both tables, selected **Close & Apply** to load the transformed data into Power BI Desktop.

---

### 🔗 2. Tournament Stage Sorting & Data Modeling

This section explains how to create a dimension table and establish relationships to display tournament stages in the correct order in the **2026 Match Timeline** visual.

For a detailed step-by-step explanation, refer to **`Stage-Sorting-and-Relationship.pdf`**.

#### 1. Create a Dimension Table

Create a dimension table named `Dim Stage` to define the correct sequence of tournament stages, from the Group Stage to the Final.

**Steps:** Modeling → New Table → Enter the DAX syntax → Press Enter.

**DAX Syntax:**

```dax
Dim Stage =
DATATABLE(
    "Stage", STRING,
    "SortOrder", INTEGER,
    {
        {"Group Stage", 1},
        {"Round of 32", 2},
        {"Round of 16", 3},
        {"Quarterfinals", 4},
        {"Semifinals", 5},
        {"Third Place Match", 6},
        {"Final", 7}
    }
)
```

#### 2. Verify the Dimension Table

In **Table View**, verify that all tournament stages and their corresponding sort-order values are correct.

**Screenshot: Dimension Table Structure**

<p align="center">
  <img src="https://github.com/shubham-2359/fifa-world-cup-analytics-powerbi-dashboard/blob/master/assets/dim-stage-table.png" alt="Dim Stage table structure" height="350" width="35%"/>
</p>

#### 3. Create the Relationship

In **Model View**, connect the `Stage` column in the 2026 match schedule table to the corresponding `Stage` column in the `Dim Stage` table.

Configure the relationship as **Many-to-One (*:1)**, with the match table on the many side and the dimension table on the one side. Ensure the relationship is active.

**Screenshot: Table Relationship**

<p align="center">
  <img src="https://github.com/shubham-2359/fifa-world-cup-analytics-powerbi-dashboard/blob/master/assets/stage-relationship.png" alt="Relationship between the match schedule and Dim Stage tables" height="650" width="55%"/>
</p>

#### 4. Verify the Data Model

Confirm that the relationship connects both tables correctly and displays the expected cardinality.

```text
2026 Match Schedule (*) ─── (1) Dim Stage
```

<p align="center">
  <img src="https://github.com/shubham-2359/fifa-world-cup-analytics-powerbi-dashboard/blob/master/assets/data-model.png" alt="Power BI data model" height="600" width="65%"/>
</p>

The `Dim Stage` table provides the intended stage sequence for the **2026 Match Timeline** visual.

To apply the order, select the `Stage` column in `Dim Stage`, choose **Sort by column → SortOrder**, and use the dimension table's stage field in the visual where appropriate.

---

### 🧮 3. DAX Measures

The following measures were created using **Modeling → New Measure**.

**Note:** The table and column names in these formulas must match the names in your Power BI model exactly.

#### 1️⃣ Total World Cups

```dax
Total World Cups = COUNT('Historical Win'[Year])
```

📌 Counts nonblank year values in the historical table. <br>
This represents the number of historical edition rows only when each edition is represented by one row.

#### 2️⃣ Total Matches

```dax
Total Matches = SUM('Historical Win'[Matches])
```

📌 Adds the match totals recorded across historical rows.

#### 3️⃣ Total Goals

```dax
Total Goals = SUM('Historical Win'[Total Goals])
```

📌 Adds the recorded goals across historical rows.

#### 4️⃣ Average Attendance

```dax
Avg Attendance = AVERAGE('Historical Win'[Avg Attendance ])
```

📌 Calculates the average of the per-edition average-attendance values.

#### 5️⃣ Matches Played

```dax
Matches Played = COUNT(FIFA_WC2026_Matches[Match_ID])
```

📌 Counts the match IDs in the 2026 scheduled. 

#### 6️⃣ Host Countries

```dax
Host Countries = DISTINCTCOUNT(FIFA_WC2026_Matches[Host_Country])
```

📌 Counts distinct host-country labels represented in the schedule.

#### 📌 Important Measure Notes

- Total Matches and Total Goals include the values recorded in every historical row, including a 2026 summary row.
- Avg Attendance is an unweighted average of edition-level averages.
- Host Countries depends on consistent country labels.
- Matches Played counts schedule records and does not independently verify match completion.
  
---

### 🎛️ 4. Dashboard Filters

The dashboard includes six interactive slicers.

| Filter | Purpose |
|---|---|
| **🏆 Champion Country** | Filters historical records by champion-country value |
| **🌍 Host Country** | Focuses analysis on a selected host country |
| **🏟️ Stage** | Filters matches by tournament stage |
| **📅 Year** | Selects a tournament edition for historical analysis |
| **🗓️ Match Date** | Filters the schedule by match date |
| **🏟️ Stadium** | Focuses on fixtures assigned to a selected venue |

**Interactive experience:** Users can combine filters to explore specific countries, tournament editions, dates, stages, and stadiums.

**Modeling note:** Slicer behavior depends on relationships between tables and visual interaction settings. Verify these in Power BI's **Edit interactions** view to ensure the intended visuals respond to each filter.

---

### 📊 5. Dashboard Visualizations

#### 🏆 KPI Cards

Six cards provide a high-level overview of the project.

- **Total World Cups:** Historical edition rows represented in the dataset.
- **Total Matches:** Match totals recorded in the historical table.
- **Total Goals:** Goals recorded in the historical dataset.
- **Avg Attendance:** Average of the edition-level average-attendance values.
- **Host Countries:** Distinct host-country labels in the 2026 schedule.
- **Matches Played:** Match records in the 2026 schedule.

#### 📊 Most Successful Nations by World Cup Titles

**Visual:** Bar Chart <br>
Ranks nations according to their World Cup title counts.

**Key purpose:** 
- Identify leading championship-winning nations.
- Compare title counts across countries.
- Highlight historical dominance in the tournament.

#### ⚽ World Cup Trends: Goals & Avg Attendance (1930–2026)

**Visual:** Combined Trend Chart <br>
Compares total goals and average attendance across tournament editions.

**Key purpose:** 
- Explore historical scoring trends.
- Observe changes in attendance.
- Identify notable variations across editions.

Interpretation should account for changes in tournament format, participating teams, match counts, and data coverage.

#### 🍩 2026 Match Distribution by Stage

**Visual:** Doughnut Chart <br>
Displays the proportion of scheduled matches allocated to each tournament stage.

**Key purpose:**
- Compare the Group Stage with knockout rounds.
- Understand the distribution of fixtures.
- Examine the number of matches at each stage.

#### 🌍 Attendance by Host Nation (1930–2026)

**Visual:** Geographic Map + Table <br>
Combines geographic context with a detailed attendance table.

**Key purpose:**
- Explore host-country attendance information.
- Compare historical attendance figures.
- Review detailed values in tabular form.

Interpretation depends on the attendance field and aggregation used in the visual.

#### 📅 2026 Match Timeline

**Visual:** Timeline-Style Column Chart <br>
Displays scheduled matches across tournament dates, with colors distinguishing tournament stages.

**Key purpose:**
- Review match distribution over time.
- Identify dates with multiple fixtures.
- Examine the timing of different tournament stages.
- Explore the tournament schedule chronologically.

The `Dim Stage` table provides the intended tournament-stage order.

#### 🏟️ 2026 Matches by Stadium

**Visual:** Treemap <br>
Compares stadiums by the number of scheduled match records assigned to each venue.

**Key purpose:**
- Compare fixture allocation across venues.
- Identify stadiums with relatively high match volumes.
- Explore the distribution of matches across host cities.

Larger tiles represent more scheduled match records.

---

## 🔍 Key Insights

Based on the values described in the dashboard, the following observations are highlighted.
### 🏆 1. Brazil Leads the Historical Title Ranking

Brazil is shown with 5 titles, followed by Germany and Italy with 4 titles each, and Argentina with 3 titles.

### 📈 2. Historical Trends Need Context

Goals and avg attendance should be interpreted alongside changes in tournament size, number of matches, participating teams, and format.

### 📅 3. The 2026 Schedule Contains 104 Match Records

The supplied schedule represents 104 fixtures for the expanded 2026 tournament. These records should be interpreted as scheduled matches unless completion information is available.

### 🍩 4. The Group Stage Represents Approximately 69.23% of Fixtures

The dashboard shows 72 Group Stage matches out of 104 scheduled match records. 
This means that most fixtures are allocated to the opening phase of the tournament.

### 🏟️ 5. Stadium Fixture Allocation Varies

The stadium treemap highlights differences in scheduled match volumes across venues, helping users compare the distribution of fixtures.

**Data caution:** Verify any 2026 historical summary values against final official records before presenting them as confirmed tournament outcomes.

---

## 💡 Business Recommendations

### 1. 🏟️ Optimize Stadium Operations

Use scheduled fixture counts to support venue staffing, cleaning, security, crowd management, and transport planning.

### 2. 📅 Improve Schedule Coordination

Use the match timeline to identify busy dates and coordinate logistics, broadcast operations, and venue turnaround.

### 3. 👥 Evaluate Attendance With Additional Context

Compare attendance with stadium capacity, match counts, tournament format, and occupancy rates where available.

### 4. 📈 Investigate Historical Trends

Analyze changes in goals and attendance alongside tournament size, host location, and other relevant factors before drawing conclusions about causes.

### 5. 🌍 Maintain Consistent Country Labels

Standardize country and stage names to reduce duplicate categories and improve dashboard filtering.

### 6. ✅ Separate Fixtures From Completed Results

Maintain a distinction between scheduled matches and completed games. Incorporating verified results and match-status fields will make future analysis more reliable.

---

## 🔮 Future Scope

- ⚽ **Team Performance Analysis:** Add match scores, wins, losses, draws, goals scored, goal difference, and team progression.
- 👥 **Advanced Attendance Analytics:** Include stadium capacity, occupancy rates, and attendance per match.
- 🧱 **Enhanced Data Modeling:** Introduce dedicated date, team, country, and stadium dimension tables.
- 🔄 **Automated Data Refresh:** Develop a reliable process for updating and validating the source data.
- 📊 **Advanced Analytics:** Add head-to-head comparisons, team-level drill-through pages, and deeper historical performance analysis.

---

## 🤝 Author

**👨‍💻 Shubham Maurya**
<br>
  <em>Data Analyst (Fresher) | Power BI Developer | Data Visualization Enthusiast</em>
<br>

  <a href="https://www.linkedin.com/in/shubham-maurya-a53b57c59/">
    <img src="https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin" alt="LinkedIn Profile"/>
  </a>
</p>

---

## ⚖️ Disclaimer

This is an independent data analytics project created for educational, research, and portfolio purposes.<br>
The dataset was independently compiled using publicly available information. This project is not affiliated with or endorsed by FIFA.

---

<p align="center">
  ⚽ <strong>Dream. Believe. Achieve.</strong> 🏆
  <br/>
  <em>Turning World Cup Data into Meaningful Insights.</em>
  <br/>
  <sub>Thank you for visiting my project.</sub>
</p>
