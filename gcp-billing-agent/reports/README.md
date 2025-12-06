# Reports Directory

This directory contains pre-configured report templates and SQL queries that the GCP Billing Agent uses to analyze costs, utilization, and performance across various Google Cloud Platform services.

## Purpose

The reports directory serves as the repository for:
- **Cost Analysis Templates**: Pre-built queries for identifying spending patterns and cost optimization opportunities
- **Utilization Reports**: Templates for monitoring resource usage across Compute Engine, GKE, Cloud SQL, Kafka, and other services
- **Performance Analytics**: Reports that help identify underutilized resources and optimization potential
- **Billing Intelligence**: Comprehensive analysis of GCP billing data for cost management

## Report Categories

### Cost Analysis Reports
- Billing breakdown by project, service, and SKU
- Daily, weekly, and monthly cost trend analysis
- Top cost contributors identification
- Cost projection and forecasting

### Resource Utilization Reports
- CPU, memory, and disk utilization across services
- Compute Engine instance performance analysis
- Kubernetes cluster resource monitoring
- Cloud SQL database utilization metrics

### Service-Specific Reports
- **Compute Engine**: Instance lists, CPU utilization, performance metrics
- **Google Kubernetes Engine**: Node utilization, cluster performance
- **Cloud SQL**: Database performance, resource usage, optimization opportunities
- **Kafka (Managed)**: Cluster utilization, capacity planning, cost analysis
- **BigQuery**: Query cost analysis, expensive query identification

## How Reports Work

1. **Template Based**: Each report is a JSON configuration containing SQL queries and metadata
2. **Automated Execution**: Reports are automatically executed by the agent's workflows
3. **Data Sources**: Reports query BigQuery billing exports and Google Cloud Monitoring APIs
4. **Parameterized**: Reports include configurable thresholds, time ranges, and filters
5. **Actionable Output**: Results provide specific recommendations for cost optimization

## Integration with Workflows

These report templates are utilized by the agent's main workflow (`gcp-underutilization-report`) to:
- Identify underutilized resources
- Calculate potential cost savings
- Generate optimization recommendations
- Provide automated alerts and insights

This directory forms the analytical foundation of the GCP Billing Agent's cost optimization capabilities.
