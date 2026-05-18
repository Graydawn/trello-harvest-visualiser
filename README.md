# Trello & Harvest Time Visualizer

A completely client-side, single-page application (SPA) that merges your Trello project estimates with your Harvest time tracking data. It generates a comprehensive, presentation-ready dashboard to analyze estimated vs. actual effort, helping you track budget health and time distribution.

## 🚀 Features

* **Zero Setup & 100% Private:** No API keys, no server, and no database required. All data processing happens entirely within your web browser.
* **Visual Budget Health:** Quickly identify which tasks are on track and which are over budget using interactive charts.
* **Detailed Breakdowns:** View time distribution by Trello list and see granular progress bars for every assigned card.
* **Print-Ready:** Optimized layout for printing or saving to PDF for sprint retrospectives and performance reviews.

## ⚠️ Important Prerequisites & Data Formatting

For the visualizer to successfully match your Trello cards with your Harvest time entries, you must follow these two formatting rules:

### 1. The Trello Shortlink Rule
When tracking time in Harvest, **you must include the Trello card's shortlink in the Harvest "Notes" field.** * **Example:** If your Trello card URL is `https://trello.com/c/yVNFFbOP/123-task-name`, the shortlink is `yVNFFbOP`. 
* Your Harvest note can contain other text, as long as the shortlink is present (e.g., `"Working on backend logic yVNFFbOP"`).

### 2. The Trello Points Rule
To calculate "Estimated Time," the app reads points directly from your Trello card titles. You must append points to the end of the card title using a double-dash or single-dash format.
* **Format:** `Card Name -- X pts` (e.g., `Setup Database -- 2 pts` or `Fix Login Bug - 0.5 pts`).
* **Hours Mapping:** The app automatically converts points to maximum estimated hours using the following scale:
    * `0 pts` = 1 Hour
    * `1 pt` = 5 Hours
    * `2 pts` = 10 Hours
    * `3 pts` = 15 Hours
    * `>3 pts` = Points * 5 Hours

## 🛠️ How to Use the Tool

### Step 1: Export Your Trello Board
1. Open your Trello Board.
2. Click the **three dots (...)** in the top right menu to show the board menu.
3. Click **More** > **Print and Export**.
4. Select **Export as JSON**.
5. Save the `.json` file to your computer.

### Step 2: Export Your Harvest Time Report
1. Log in to Harvest and navigate to the **Reports** > **Detailed Time** section.
2. Filter the report for the desired timeframe and your user account.
3. Click the **Export** button and select **CSV**.
4. Save the `.csv` file to your computer.

### Step 3: Generate Your Dashboard
1. Open the `trello_harvest_visualizer.html` file in any modern web browser.
2. Click **Upload Trello Board JSON** and select the file from Step 1.
3. A dropdown will appear. **Select your Trello Username** from the list so the app knows which cards are assigned to you.
4. Click **Upload Harvest CSV Report** and select the file from Step 2.
5. Click **Generate Dashboard**.

## 💻 Tech Stack

This tool is built as a lightweight, single-file HTML document using:
* [Vue.js 3](https://vuejs.org/) (Frontend Framework logic)
* [Tailwind CSS](https://tailwindcss.com/) (Styling)
* [Chart.js](https://www.chartjs.org/) (Data visualization)
* [PapaParse](https://www.papaparse.com/) (Client-side CSV parsing)

Disclaimer: This was created with AI.
