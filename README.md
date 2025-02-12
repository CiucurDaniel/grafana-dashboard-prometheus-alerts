# Grafana Dashboard Prometheus Alerts

This dashboard provides insights into Prometheus alerting rules and their current states, helping teams monitor active alerts and alert configurations. The dashabord is using Prometheus API as datasource.

## Requirements

The target **Grafana** instance need to have [Infinity Datasource](https://grafana.com/grafana/plugins/yesoreyeram-infinity-datasource/) plugin installed.

## Data Sources

- **Yesoreyeram Infinity Datasource**: Used for handling JSON-based queries.
- **Prometheus API**: Retrieves alert rules and their states.

## Panels

### 1. Total Firing Alerts
- **Description**: Displays the count of currently firing alerts.
- **Data Source**: Prometheus API (`/api/v1/rules?type=alert`)
- **Thresholds**:  
  - Green: No alerts  
  - Red: At least 1 alert  

### 2. Total Alerts Configured
- **Description**: Shows the total number of alert rules configured.
- **Data Source**: Prometheus API (`/api/v1/rules?type=alert`)

### 3. Firing Alerts Table
- **Description**: Displays details of currently firing alerts.
- **Data Source**: Prometheus API
- **Fields**:
  - `alertname`
  - `summary`
  - `severity`
  - `instance`
  - `namespace`

### 4. Alert Collection
- **Description**: Shows all configured alerts along with their descriptions.
- **Data Source**: Prometheus API
- **Fields**:
  - `name`
  - `summary`
