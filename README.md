# Azure Monitoring Strategy

## Problem statement

Is is difficult to respond to a service outage or performance degradation issues. Logs and Matrics may be located in service metrics and logs, Log Analytics Workspaces, and Insights Workspaces. These problems usually occur at time when the solution is not actively being monitored. It is difficult to corralate issues particularly issues related to dependent services.

## Objective of a monitoring strategy

Quickly respond to a service outage or performance degradation issues by having a strategy that allows for a faster investigation/root cause analysis and processes to respond to the outage based on the findings.

## Using Dashboards vs Alerts

Alerts constantly monitor the health of the systems and raise notification when issues are discoverd. Dashboards can help to quickly get health status of all running systems and help correlate service events. 

## Topdown monitor strategy

- Azure Services Health
- Dependent Service Health (CPU utilization, Memory utilization, Data utlization, HD Storage)
- Application Health with Application Insights
  - Availability
  - 5XX
  - 4XX; particularly login failures and not founds
  - Failed Dependemy calls
  - Performance degradation (not meeting NFRs)
  - Exceptions
  - Custom events
  - Traces

## Resiliency and self healing

Examples:
- Review resiliency in architecture
- Fail to a secondary region automatically or be ready to failover manually
- Have resilient application architectures, for example:
  - Save data to queues instead of database
- Have a process to perform root cause analysis
- Use CI/CD pipelines to deploy hotfixes
- Build a KB of issues and fixes

