# IPL Match Dataset Exploratory Data Analysis (EDA)

This project contains an initial exploratory data analysis and data preprocessing workflow for the Indian Premier League (IPL) matches dataset (spanning from 2008 to 2024 seasons).

## Dataset Overview

The dataset provides comprehensive information regarding IPL matches played between 2008 and 2024.

* **Raw Records:** 1,095 matches
* **Cleaned Records:** 1,028 matches (after dropping missing values)
* **Features:** 19 parameters detailing match metadata, venue, teams, toss outcomes, results, and officiating umpires.

### Features Description
- `id`: Unique match identifier
- `season`: IPL season year (e.g., 2007/08 to 2024)
- `city`: Location where the match took place
- `date`: Match date (`YYYY-MM-DD`)
- `match_type`: Stage of the tournament (e.g., League, Qualifier 1, Eliminator, Qualifier 2, Final)
- `player_of_match`: Player awarded Man of the Match
- `venue`: Stadium name
- `team1`, `team2`: Participating teams
- `toss_winner`: Team that won the coin toss
- `toss_decision`: Decision after winning toss (`bat` or `field`)
- `winner`: Winning team
- `result`: Outcome type (`runs` or `wickets`)
- `result_margin`: Win margin value
- `target_runs`, `target_overs`: Target score and overs set for the chasing team
- `super_over`: Indicates whether a Super Over was played (`N` / `Y`)
- `umpire1`, `umpire2`: On-field umpires

## Data Preprocessing Pipeline

The notebook executes standard data hygiene and cleaning procedures:

1. **Environment Setup & Load:**
   - Import `pandas` library.
   - Load dataset from `matches.csv`.

2. **Exploratory Data Inspection:**
   - Inspect dataset structure using `.head()`, `.tail()`, `.shape`, and `.columns`.
   - Structural audit via `.info()` and summary statistics using `.describe()`.

3. **Data Cleaning & Sanitation:**
   - **Duplicate Detection:** Checked for duplicate records (`df.duplicated().sum()`).
   - **Feature Drop:** Removed sparse and redundant feature column `method` (`df.drop(columns="method", inplace=True)`).
   - **Null Value Handling:** Analyzed missing values across features and cleaned incomplete records via `.dropna()`.

## Setup & Execution

### Prerequisites
Ensure Python 3.x and Pandas are installed in your environment.

```bash
pip install pandas
