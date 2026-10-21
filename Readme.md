# Niti_aayog_intern
# WEP States Tracker: Interactive Tableau Dashboard

An interactive Tableau dashboard that tracks how States and Union Territories are progressing in onboarding the **Women Entrepreneurship Platform (WEP)**. I built it during my internship at **NITI Aayog**.

[![Dashboard preview](![alt text](<Screenshot 2026-10-21 at 1.08.43 PM.png>))]

> **Data note:** The data is not included in this repository. Figures shown in the screenshots are limited to what is already public or has been cleared for display.

---

## Problem

Tracking WEP rollout across many States and UTs in a spreadsheet makes it hard to see at a glance:

- which States have onboarded and which haven't,
- which stage of the process each State is at,
- what the pending steps are and what they depend on.

## Solution

A three-view dashboard that turns the State-wise tracker into one visual, drill-down interface.

### 1. Frontend (landing page)
A title and navigation screen that sends the user to either view below.

### 2. Onboarding Status
- **India map** (filled polygons) showing each State/UT's onboarding status, and used to select a State.
- **KPI cards:** Overall Progress %, Steps Pending, and WEP Centre Established (e.g. "x / total" for *All States*, or *Established / Not established* for one State).
- **Donut charts** showing stage-wise completion (completed vs remaining).
- **Bar chart** of completion by stage.
- **Status table** with stage, step and status for the selected State.

### 3. Way Forward
- The same State selector, but focused on **pending steps**.
- KPI cards for overall progress, centre established and steps pending.
- Stage-wise donuts and a chart for the selected State.
- A **Way Forward table** listing each pending step with its **dependency** and **remarks**, so the next action is clear.

## Features and Tableau techniques

- **Parameters:** `Selected State` and `Dashboard View` drive the whole dashboard, with an "All States" option for the national view.
- **Dashboard actions:** clicking a State on the map filters every chart and KPI.
- **Calculated fields:**
  - conditional aggregations, e.g. `SUM(IF [State] = [Parameter] AND [Status] = "Yes" THEN 1 ELSE 0 END)` for completed steps,
  - completion and remaining percentages, formatted KPI strings, and dynamic labels.
- **Dynamic KPIs** that change between *All States* and single-State views (`COUNTD`, `IF/ELSE` logic).
- **Donut charts** built with dual-axis pie marks and a centre label.
- **Filled map** of India using geographic roles.
- **Multi-dashboard navigation** with a custom layout using containers, images and buttons.
- **Data prep:** the tracker data was cleaned and structured in a spreadsheet (State, Stage, Step, Dependency, Status, Remarks) before being connected to Tableau.

## Tools

Tableau Desktop · Tableau Public · Google Sheets / Excel

## My role

I designed and built the dashboard end to end: structuring the tracker data, writing the calculated fields and parameters, designing the visuals and layout, and publishing it.

## Impact

- Replaced a row-by-row tracker with a single view of State-wise progress.
- Made pending steps and their dependencies easy to find for follow-up.
- Gave a quick national summary and State-level drill-down in one place.

## Screenshots

| Onboarding Status | Way Forward |
|---|---|
| ![Onboarding Status](images/onboarding-status.png) | ![Way Forward](images/way-forward.png) |

## Links

- Live dashboard: [Tableau Public](YOUR_TABLEAU_PUBLIC_LINK)
- Author: [Your Name](https://github.com/YOUR_GITHUB_USERNAME)

---

*Built as part of my internship at NITI Aayog. This is an independent portfolio project and is not an official NITI Aayog publication.*