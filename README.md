# Azure Monitoring Strategy

## Reference Guides

- https://docs.microsoft.com/en-us/learn/modules/design-monitoring-strategy-on-azure/

## Problem statement

Is is difficult to respond to a service outage or performance degradation issues. Logs and Matrics may be located in service metrics and logs, Log Analytics Workspaces, and Insights Workspaces. These problems usually occur at time when the solution is not actively being monitored. It is difficult to corralate issues particularly issues related to dependent services.

## Objective of a monitoring strategy

Quickly respond to a service outage or performance degradation issues by having a strategy that allows for a faster investigation/root cause analysis and processes to respond to the outage based on the findings.

## Using Dashboards vs Alerts

Alerts constantly monitor the health of the systems and raise notification when issues are discoverd. Dashboards can help to quickly get health status of all running systems and help correlate service events. 

## Topdown monitor strategy

- Azure Services Health
- Dependent Service Health (CPU utilization, Memory utilization, Data utlization, HD Storage,etc.)
  - Rember global services such as AAD
  - And even services such as ExpressRoute, really any service that has an SLA
  - Consider resilincy of on-prem app if there are hard dependencies from on-prem
- Application Health with Application Insights
  - Availability
  - 5XX
  - 4XX; particularly login failures and not founds
  - Failed Dependemy calls
  - Performance degradation (not meeting your NFRs)
  - Exceptions types and counts
  - Custom events
  - Traces (is the exception information in the traces, extract it via KQL)

## Consider your resiliency

- Review resiliency in architecture
  - Fail to a secondary region automatically or be ready to failover manually
- Have resilient application architectures, for example:
  - Save data to queues instead of database in case of database outage
  - Use eventual consistency and decoupling
  - Include retry logic

## Have troubleshooting/root cause analysis plan

- Have a process to perform root cause analysis
- Use CI/CD pipelines to deploy hotfixes
- Build a KB of issues and fixes
- Have a retrospective and incorporate learnings into the overall strategy
