# GCP Billing Agent

## Overview

The GCP Billing Agent is an intelligent cost optimization and billing analysis agent designed to help organizations monitor, analyze, and optimize their Google Cloud Platform spending. This agent automatically identifies underutilized resources, tracks cost trends, and provides actionable recommendations to reduce cloud expenses.

## What This Agent Does

### Primary Functions
1. **Cost Analysis & Monitoring**
   - Analyzes GCP billing data to identify top cost contributors by project and service
   - Tracks daily, weekly, and monthly spending patterns
   - Monitors cost trends across different GCP services and SKUs

2. **Resource Utilization Assessment**
   - Examines Google Cloud Monitoring metrics to determine utilization rates
   - Calculates CPU, memory, and usage metrics for various services
   - Identifies services with utilization below optimal thresholds

3. **Underutilization Detection**
   - Automatically detects underutilized services across your GCP infrastructure
   - Calculates potential cost savings from rightsizing or eliminating resources
   - Provides specific recommendations for each underutilized service

4. **Automated Reporting & Alerts**
   - Generates comprehensive cost optimization reports
   - Sends automated alerts and summaries via Slack
   - Provides actionable insights with prioritized action items

### Key Capabilities
- **BigQuery Integration**: Queries billing export data for detailed cost analysis
- **Monitoring Integration**: Leverages Google Cloud Monitoring for resource utilization metrics
- **Automated Workflows**: Runs scheduled analysis (daily at midnight) via the `gcp-underutilization-report` workflow
- **Multi-Service Analysis**: Covers Compute Engine, GKE, Cloud SQL, Kafka, BigQuery, and more
- **Cost Projections**: Provides daily cost breakdowns and monthly projections
- **Remediation Guidance**: Offers specific recommendations for cost optimization

## Directory Structure

- **`reports/`** - Pre-configured report templates for various GCP services and cost analysis
- **`knowledge/`** - Configuration data including primary region settings and operational knowledge
- **`datasources/`** - Connection configurations for BigQuery, Cloud Monitoring, and notification systems
- **`workflows/`** - Automated workflow definitions for scheduled cost analysis

## Main Workflow

The agent's primary workflow (`gcp-underutilization-report`) performs the following steps:

1. Query BigQuery billing data to identify top cost contributors by project
2. Examine Google Cloud Monitoring metrics for utilization rates
3. Calculate utilization percentages using CPU, memory, and usage metrics
4. Identify services with below-threshold utilization as underutilized
5. Calculate daily costs, projected monthly costs, and potential savings
6. Generate remediation recommendations for each underutilized service
7. Compile findings into an actionable cost optimization report
8. Send summary notifications via Slack

This workflow runs automatically on a daily schedule to ensure continuous cost monitoring and optimization.
