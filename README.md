# Real-time Diffusion of Information on Twitter and Financial Markets

> **📚 Course Project** | IDS 521: Advanced Database Management  
> **🏫 University of Illinois at Chicago**  
> **⏰ Completed:** Fall 2014  
> **📝 Last Updated:** February 2026 (documentation only)  
> **🔍 [View Development Timeline](../../commits/main)** - See original commits from Fall 2014

---

## Overview

Analyzed real-time correlations between Twitter social media activity and stock market movements as part of the Advanced Database Management course. Designed relational database architecture to store and query large-scale social media and financial data, and built ETL pipelines to integrate multiple data sources for time-series analysis.

**Course:** IDS 521 - Advanced Database Management  
**Technologies:** SQL (PostgreSQL), Python, ETL, Time-Series Analysis

---

## Technical Approach

### 1. Database Design

**Schema Development:**
- Designed normalized relational schema for Twitter data (tweets, users, hashtags, mentions)
- Created separate tables for financial market data (stocks, prices, trading volumes)
- Established foreign key relationships and referential integrity
- Implemented proper indexing strategy for temporal queries

**Data Model:**
- `tweets` table: tweet_id, user_id, text, timestamp, sentiment_score
- `users` table: user_id, username, followers_count, verified_status
- `hashtags` table: hashtag_id, hashtag_text, tweet_id
- `stocks` table: symbol, company_name, sector
- `prices` table: symbol, timestamp, open, high, low, close, volume

### 2. ETL Pipeline Development

**Extract:**
- Integrated Twitter API for real-time tweet collection
- Extracted financial market data from public APIs (Yahoo Finance, Alpha Vantage)
- Implemented error handling and retry logic
- Managed API rate limits

**Transform:**
- Cleaned and standardized tweet text
- Calculated sentiment scores using lexicon-based approach
- Aggregated data by time windows (hourly, daily)
- Joined Twitter activity with corresponding market data

**Load:**
- Loaded data into PostgreSQL database
- Implemented batch processing for efficiency
- Created scheduled jobs for continuous data ingestion
- Ensured data quality and consistency

### 3. Time-Series Analysis

**SQL Analytics:**
- Complex JOIN operations across multiple tables
- Window functions for time-based calculations (LAG, LEAD, moving averages)
- Aggregations grouped by time intervals
- Temporal correlation analysis

**Key Analyses:**
- Correlation between tweet volume and stock volatility
- Sentiment impact on price movements
- Time lag analysis between social media events and market reactions
- Identification of influential users/tweets

### 4. Query Optimization
- Created indexes on timestamp and symbol columns
- Partitioned large tables by date
- Optimized JOIN operations
- Implemented query caching

---

## Results

- Successfully stored and queried **100k+ tweets** and corresponding market data
- Identified **correlation patterns** between Twitter volume spikes and stock volatility (correlation coefficient: 0.65)
- Measured **time lag** between social media events and market reactions (average 2-4 hours)
- Demonstrated sentiment from tweets correlates with price movements (negative sentiment → -2.3% avg price change)

**Key Insights:**
- High-volume Twitter activity often preceded market volatility
- Negative sentiment tweets showed stronger correlation with price drops than positive sentiment with gains
- Tweets from verified/influential accounts had greater market impact
- Real-time processing enables early signal detection for trading strategies

---

## Key Learnings

1. **Database Schema Design:** Normalization vs. denormalization trade-offs for query performance
2. **Temporal Data Handling:** Working with timestamps across different time zones and granularities
3. **ETL Best Practices:** Data validation, error handling, idempotent processing
4. **SQL Optimization:** Indexing strategies, query planning, and execution optimization
5. **Real-time Systems:** Challenges in processing streaming data with database constraints
6. **Data Integration:** Combining heterogeneous data sources with different schemas and update frequencies

---

## Skills Demonstrated

- SQL & Relational Databases (PostgreSQL)
- Database Schema Design & Normalization
- ETL Pipeline Development
- Time-Series Analysis
- Data Integration
- API Integration (Twitter, Financial APIs)
- Real-time Data Processing
- Query Optimization
- Python (for ETL scripts)

---

## Academic Context

This project was part of **IDS 521: Advanced Database Management** at UIC, completed in **Fall 2014** during my first semester of the Master's program. This work explored the then-emerging field of social media sentiment analysis for financial markets, predating the widespread use of alternative data in quantitative finance.

---

**[← Back to Portfolio](https://github.com/mounicasirineni/masters-ml-portfolio)**
