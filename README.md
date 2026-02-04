# powerbi-daily-plan-vs-actual-dashboard
Power BI project monitoring daily production by comparing planned vs actual output. Data is collected via Google Forms, stored in Sheets, and analyzed with DAX measures. Visuals highlight performance, variance, and trends for effective production management.
# Power BI Daily Plan vs Actual Dashboard

This repository contains the Power BI project files and related resources for a **Daily Plan vs Actual Dashboard** designed to monitor and analyze production performance. The dashboard provides insights by comparing planned production counts against actual counts, visualizing variance, and supporting data-driven decision-making.

---

## Project Overview

The dashboard integrates data collected via Google Forms, stored in Google Sheets, and visualized in Power BI. It enables real-time tracking and analysis of daily production plans vs actual outputs along with variance calculations.

### Key Features
- Visualize daily planned product counts vs actual counts.
- Calculate and display variance and percentages for better performance tracking.
- Group data by Day Name and Month Name for temporal insights.
- Simple deployment process connecting Power BI directly to Google Sheets.

---

## Data Sources

- **Google Form**: Used for entering daily production data including planned and actual counts.
- **Google Sheet**: Stores the responses collected via the Google Form.
- **Power BI**: Connects to Google Sheets to import data and build visual reports.

---

## Power BI Data Preparation

After connecting to the Google Sheet, the data table is imported and renamed as `Form Responses 1`. Additional calculated columns and measures are created as follows:

### Calculated Columns

| Column Name | Formula / Description |
| ----------- | --------------------- |
| **Day Name** | `Day Name = FORMAT('Form Responses 1'[Date], "DDDD")`<br>Extracts the day of the week name (e.g., Monday, Tuesday) from the Date field. |
| **Month Name** | `Month Name = FORMAT('Form Responses 1'[Date], "MMMM")`<br>Extracts the full month name from the Date field. |
| **Variance** | `Variance = 'Form Responses 1'[Actual Count of Product] - 'Form Responses 1'[Plan Count of Product]`<br>Calculates the difference between actual and planned product counts. |

### Measures

| Measure Name       | DAX Formula                                                                                         | Description                                           |
|--------------------|---------------------------------------------------------------------------------------------------|-------------------------------------------------------|
| **Actual %**       | Actual % = DIVIDE( SUM('Form Responses 1'[Actual Count of Product]), SUM('Form Responses 1'[Plan Count of Product]), 0 )| Calculates the percentage of actual count over planned count. |
| **Plan %**         | `Plan % = 100`                                                                                     | Constant 100% for planned production.                  |
| **Variance %**     | Variance % = DIVIDE( SUM('Form Responses 1'[Actual Count of Product]) - SUM('Form Responses 1'[Plan Count of Product]), SUM('Form Responses 1'[Plan Count of Product]), 0 )| Calculates the percentage variance between actual and planned counts. |

---

## Deployment Instructions

1. **Get the Google Sheets Data Link:**
   - Open your Google Sheet containing the form responses.
   - Copy the shareable link for the sheet.

2. **Connect Power BI to Google Sheets:**
   - Open Power BI Desktop.
   - Go to **Get Data** > **More...**
   - Search for **Google Sheets** connector.
   - Paste the copied link and click **Connect**.
   - Grant Power BI the necessary permissions to access your Google Sheet.

3. **Prepare the Dataset:**
   - Once imported, rename the table to `Form Responses 1`.
   - Fix the first row as column headers if necessary.
   - Add the calculated columns and measures as described above.

4. **Build Your Visuals:**
   - Use the prepared data and measures to create visuals comparing plan vs actual production.
   - Include variance and percentage measures for insightful analysis.
   - Group data by Day Name or Month Name for trend insights.

---

## Recommended Visuals

- Bar chart comparing **Sum of Plan Count of Product** vs **Sum of Actual Count of Product** by Day or Date.
- Line or column chart showing **Variance** and **Variance %** over time.
- Card visuals showing overall production percentages.
- Slicers for filtering by **Day Name**, **Month Name**, or **Section**.

---

## Notes

- Ensure your Google Form and Sheet are consistently updated to maintain accurate dashboard data.
- Refresh Power BI data regularly to capture the latest form submissions.
- Adjust time zones and date formats as needed for your locale.

---

## Contributing

Feel free to fork this repository and submit pull requests to enhance the dashboard or data collection process.

---


##📬 Contact

For questions or support, please contact **Ishara Dhananjaya** on:

* Facebook
* LinkedIn
* TikTok
* Instagram

---

If you want it formatted differently or with links included, just let me know!


---

Thank you for using this Power BI Daily Plan vs Actual Dashboard project!  
Data-driven decisions lead to better production management 🚀📊

