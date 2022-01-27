# Azure Monitoring Strategy

## Problem statement

Is is difficult to respond to a service outage or performance degradation issues. Logs and Matrics may be located in service metrics and logs, Log Analytics Workspaces, and Insights Workspaces. These problems usually occur at time when the solution is not actively being monitored. It is difficult to cooralate issues particularly issues related to dependent services.

## Objective of a monitoring strategy

Be able to quickly respond to service outage issues by having a strategy to perform the outage investigation/root cause analysis and eventually respond to outages.

## Using Dashboards vs Alerts

Alerts constantly monitor the health of the systems and raise notification when issues are discoverd. Dashboards are usefult to have all the information handy in one place handy once alerts have been raised. 

## Topdown monitor strategy

- Azure Services Health
- Depender Service Health (CPU utilization, Memory utilization, Data utlization, HD Storage)
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

## Using Log Diagnostics

- Enable sending activity log and metrics to a log analytics workspace if the data is needed more than X days. Otherwise, all telemtry is available for the last 7 days.

## Implementation

### Azure Service Health

- Create an alert service health issues for the subscription, global services and all Azure Services in your solution

### Dependent Service Health

### Application Health with Application Insihgts
