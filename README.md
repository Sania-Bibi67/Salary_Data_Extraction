# Salary Data Extraction

## Overview

This project contains two apps:
### App1
App1 sends alphabetic keys via an HTTP Trigger to salary-jobtitle-keys queue. Queue Trigger 1 fetches job titles and sends them to another queue, while Queue Trigger 2 scrapes the titles and stores them in the database.

### App2
App2’s HTTP Trigger retrieves job titles from the database and sends them to salary-queue1. Queue Triggers then generate links, scrape location-specific data, and finally extract salary details, storing everything in the database.

## Setup

### Environment Variables
Add following variables in local.settings.json file:
- `DbServer`: SQL Server name.
- `DbName`: Database name.
- `DbUsername`: Database username.
- `DbPassword`: Database password.
- `DbTableName`: Database table name where the data will be inserted.

### Dependencies

Install the required Python packages listed in requirements.txt:

```bash
pip install -r requirements.txt
 