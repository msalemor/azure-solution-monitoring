# azure-solution-monitoring

## Problem statement

Is is difficult to respond to a service outage becase it is difficult to locate, corralate, debug and deploy fix  solution in the form of service being down and service degradation. These problems may occur when the solution is not being monitored. Dashboard is usefult to have the information handy once there's an alert for an issue.

## Objective of a monitoring strategy

Have a strategy to perform root cause analysis, deploy a fix, raise a support ticket, etc. 

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


## Ideal solution including self healing

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
