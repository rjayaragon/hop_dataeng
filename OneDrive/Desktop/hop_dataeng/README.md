# GitHub Repository Analytics Platform

GitHub repository analytics platform built with medallion architecture for collecting, cleaning, and analyzing repository metadata. Implements three-layer architecture (Bronze/Silver/Gold) for scalable analytics.

## Project Status

Current development progress:
- Bronze Layer: Complete
- Silver Layer: Complete
- Gold Layer: In Progress

**Repository Count:** 1,270 repositories from 50 GitHub users
**Data Volume:** 1,270 rows × 7 essential columns
**Last Updated:** 2025-11-19

## Architecture

Three-layer medallion architecture designed for cloud deployment (Azure Databricks).

### Bronze Layer
Raw data collection from GitHub API with minimal transformation.
- Collects repositories from 50 GitHub users
- Stores raw API responses as JSON
- Includes error handling and retry logic
- Rate limiting: 0.5s delay between requests

**Output:** `data/bronze/2025-11-15_github_users.json`

### Silver Layer
Data cleaning and standardization with quality flags.
- Removes API error responses (3 invalid records)
- Standardizes date formats to ISO 8601 with UTC timezone
- Handles missing values: language → "Unknown", description → "No description provided"
- Reduces from 79 columns to 7 essential fields
- Adds data quality metadata

**Output:** `data/silver/2025-11-19_github_users.parquet`

### Gold Layer
Business aggregations and insights (in progress).
- Most popular programming languages
- User contribution analysis
- Repository creation trends
- Data quality metrics

## Schema

### Silver Layer Output
```
owner_login (string)     - GitHub username of repository owner
name (string)            - Repository name
description (string)     - Repository description
language (string)        - Primary programming language
stargazers_count (int)   - Number of stars
created_at (datetime)    - Creation timestamp (UTC)
updated_at (datetime)    - Last update timestamp (UTC)
```

## Setup

### Prerequisites
- Python 3.8+
- Git
- pip

### Installation

```bash
# Clone repository
git clone https://github.com/rjayaragon/hop_dataeng.git
cd hop_dataeng

# Install dependencies
pip install -r requirements.txt
```

### Dependencies
- pandas - Data manipulation and analysis
- pyarrow - Parquet file support
- pyspark - Distributed processing (future)
- pydantic - Data validation

See `requirements.txt` for complete list.

## Project Structure

```
hop_dataeng/
├── notebooks/
│   ├── bronze_github.ipynb       # Data collection from GitHub API
│   ├── silver_github.ipynb       # Data cleaning and transformation
│   └── gold_github.ipynb         # Business aggregations (in progress)
├── data/
│   ├── bronze/                   # Raw API responses
│   └── silver/                   # Cleaned and processed data
├── pipeline_design.md            # Technical specifications
├── requirements.txt              # Python dependencies
├── PROGRESS.md                   # Detailed learning journal
├── DAILY_SCHEDULE.md             # Time tracking and milestones
└── README.md                      # This file
```

## How to Run

### Bronze Layer (Data Collection)
```bash
# Open notebooks/bronze_github.ipynb
# Run all cells to collect data from GitHub API
# Output: data/bronze/2025-11-15_github_users.json
```

### Silver Layer (Data Cleaning)
```bash
# Open notebooks/silver_github.ipynb
# Loads bronze JSON and performs transformations
# Output: data/silver/2025-11-19_github_users.parquet
```

### Gold Layer (Business Analysis)
```bash
# Open notebooks/gold_github.ipynb
# Loads silver parquet and creates aggregations
# In progress - check back soon
```

## Data Quality

Current state of silver layer data:

| Metric | Value | Status |
|--------|-------|--------|
| Total Repositories | 1,270 | Complete |
| API Errors Removed | 3 | Complete |
| Missing Language | 331 (26%) | Flagged |
| Missing Description | 150 (12%) | Flagged |
| Complete Records | 1,270 (100%) | Ready for Gold |

All missing values are handled: nulls replaced with descriptive strings and flagged for downstream analysis.

## Key Decisions

**Data Retention:** Keep all 1,270 repositories despite missing language/description fields. Allows downstream analysis of data completeness impact.

**Date Handling:** Convert ISO 8601 strings to datetime64[ns, UTC] for temporal calculations and aggregations.

**Column Selection:** Reduced from 79 API fields to 7 essential columns focused on analysis needs.

**File Format:** Use Apache Parquet for silver layer (compressed, type-safe, cloud-ready).

## Roadmap

**Gold Layer (Week 2):**
- Implement 4 business aggregations
- Create summary tables and visualizations
- Generate data quality report

**Future Enhancements:**
- Build additional analytics pipelines
- Implement production monitoring and alerting
- Deploy to Azure Databricks for scalability
- Add CI/CD pipeline for automated testing

## Documentation

- `PROGRESS.md` - Detailed learning journal with blockers and solutions
- `pipeline_design.md` - Technical specifications and requirements
- `DAILY_SCHEDULE.md` - Time tracking and weekly metrics

## Author

RJ Aragon

GitHub: https://github.com/rjayaragon
