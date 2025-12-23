# Duke Football Analytics
### Calvin Chen (calvin.chen@duke.edu)

This repository organizes R- and Quarto-based analyses of Duke University football performance and fan engagement. Key workstreams focus on understanding historical attendance patterns and forecasting 2024 home-game turnout using multi-season datasets.

## Key Sections
- **Attendance (2022-23 analysis):** Uses `Duke Stats - DukeAttendanceV2.csv` to isolate home games, then tests how kickoff time, ESPN win probability, day of week, academic breaks, rainfall, and UNC rivalry status influence headcount via linear and generalized linear models with AIC comparisons for model fit.
- **AttendancePredictions2024 (2024 forecasts):** Builds attendance predictions for upcoming 2024 home games using opponent schedules and long-term records (2011–2023 base, expanded to 2001 with weather data), noting stadium capacity changes after the 2016 renovation when reporting historical baselines.

## Repository Structure
- `Attendance/` – Exploratory analysis of 2022–2023 home-game attendance drivers and model variants.
- `AttendancePredictions2024/` – Quarto notebook projecting 2024 attendance with iterative datasets and visualization outputs.
- `DukeOffense/`, `DukeDefense/`, `Roster/` – Additional football analytics projects (not covered in this document).
- `commands.log` – Command history captured during development sessions.

## Data Inputs
- `Attendance/data/Duke Stats - DukeAttendanceV2.csv` – Base table of game attributes and attendance used in the 2022–23 modeling workflow.
- `AttendancePredictions2024/data/Duke Stats - DukeAttendanceV3.csv` (and later versions V5–V7) – Home-game history for prediction training, including renovation flags and opponent metadata.

## Requirements
- R (version 4.2+ recommended) with the `tidyverse`, `tidymodels`, and `cowplot` packages installed for data wrangling, modeling, and visualization.
- [Quarto](https://quarto.org) CLI for rendering `.qmd` files to PDF.

## Running the Analyses
1. Open the project root in your R environment.
2. Render the attendance exploration: `quarto render Attendance/Attendance.qmd` (outputs `Attendance.pdf` in the same folder).
3. Render the 2024 forecasts: `quarto render AttendancePredictions2024/2024_Attendance_Predictions.qmd` (outputs `2024_Attendance_Predictions.pdf`).
4. To inspect intermediate objects, run individual code chunks interactively in RStudio or another IDE.

## Key Variables
Core fields used across the attendance workflows include opponent name, ESPN Football Power Index (FPI), kickoff time (24-hour decimal format), site (home/away/neutral), point differential, attendance counts and percent of capacity, ESPN win probability at kickoff, rainfall indicator, QB starter flag, academic break flag, national holiday flag, TV coverage, location, bowl status, and UNC rivalry indicator.

## Outputs
- `Attendance/Attendance.pdf` – Visual diagnostics and model comparisons for recent home-game attendance drivers.
- `AttendancePredictions2024/2024_Attendance_Predictions.pdf` – Scenario analyses and projected attendance by opponent for the 2024 season.
