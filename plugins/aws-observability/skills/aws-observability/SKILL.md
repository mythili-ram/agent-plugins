---
name: aws-observability
description: "Comprehensive AWS observability platform combining CloudWatch Logs, Metrics, Alarms, Application Signals (APM), CloudTrail security auditing, and automated codebase observability gap analysis. Triggers on phrases like: CloudWatch logs, metrics, alarms, monitoring, observability, application signals, APM, distributed tracing, performance, latency, errors, troubleshooting, root cause analysis, security audit, CloudTrail, log analysis, alerting, SLO, incident response, observability gaps, missing instrumentation."
---

# AWS Observability

Comprehensive AWS observability platform combining monitoring, troubleshooting, security, and optimization tools.

## Prerequisites

1. **AWS CLI configured** with credentials (`aws configure` or `~/.aws/credentials`)
2. **Python 3.10+** and `uv` installed
3. **Application Signals enabled** in your AWS account when applicable
4. **Required AWS Permissions** (read-only, least-privilege):
   - **CloudWatch Metrics & Alarms**: `cloudwatch:GetMetricData`, `cloudwatch:GetMetricStatistics`, `cloudwatch:ListMetrics`, `cloudwatch:DescribeAlarms`, `cloudwatch:DescribeAlarmsForMetric`, `cloudwatch:DescribeAlarmHistory`, `cloudwatch:DescribeAnomalyDetectors`
   - **CloudWatch Logs**: `logs:DescribeLogGroups`, `logs:DescribeLogStreams`, `logs:GetLogEvents`, `logs:FilterLogEvents`, `logs:StartQuery`, `logs:StopQuery`, `logs:GetQueryResults`, `logs:DescribeQueries`
   - **X-Ray**: `xray:BatchGetTraces`, `xray:GetTraceSummaries`, `xray:GetTraceGraph`, `xray:GetServiceGraph`, `xray:GetTimeSeriesServiceStatistics`
   - **CloudTrail**: `cloudtrail:LookupEvents`, `cloudtrail:DescribeTrails`, `cloudtrail:GetTrail`, `cloudtrail:ListTrails`, `cloudtrail:GetEventSelectors`
   - **Application Signals**: `application-signals:GetService`, `application-signals:ListServices`, `application-signals:ListServiceOperations`, `application-signals:GetServiceLevelObjective`, `application-signals:ListServiceLevelObjectives`, `application-signals:BatchGetServiceLevelObjectiveBudgetReport`
   - `synthetics:GetCanary`, `synthetics:GetCanaryRuns` for canary analysis
   - `s3:GetObject`, `s3:ListBucket` for canary artifacts
   - `iam:GetRole`, `iam:ListAttachedRolePolicies`, `iam:GetPolicy`, `iam:GetPolicyVersion` for enablement guides

## Configuration

After installing this plugin, update the MCP server configuration with your AWS profile and region. Find the `awslabs.cloudwatch-mcp-server` entry and update the `env` section:

```json
"env": {
  "AWS_PROFILE": "your-profile-name",
  "AWS_REGION": "us-east-1",
  "FASTMCP_LOG_LEVEL": "ERROR"
}
```

**Default:** Uses `default` AWS profile and `us-east-1` region.

**Quick Test:** After configuration, try: _"Show me my CloudWatch log groups"_

## Capabilities

### CloudWatch Logs

Query and analyze logs using CloudWatch Logs Insights. Supports multi-log-group queries, JSON field extraction, statistical functions, pattern detection, and anomaly analysis.

### CloudWatch Metrics & Alarms

Monitor resource performance with metric data retrieval, Metrics Insights queries, trend analysis, and recommended alarm configurations based on AWS best practices.

### Application Signals (APM)

Application performance monitoring with distributed tracing, service maps, SLOs, error budget tracking, and automatic service discovery. Includes primary audit tools (`audit_services`, `audit_slos`, `audit_service_operations`) with wildcard targeting, 100% trace visibility via `search_transaction_spans`, and canary failure analysis.

### CloudTrail Security Auditing

Security auditing and compliance tracking through CloudTrail Lake (SQL), CloudWatch Logs (real-time), or Lookup Events API (fallback). Includes IAM change monitoring, resource deletion tracking, and unauthorized access detection.

### Codebase Observability Analysis

Automated analysis of codebases to identify observability gaps across Python, Java, JavaScript/TypeScript, Go, Ruby, and C#/.NET. Covers logging patterns, metrics instrumentation, tracing coverage, error handling, and health checks.

### AWS Documentation Access

Search and read official AWS documentation for troubleshooting, best practices, and API references.

## Reference Files

Load these resources as needed for specific guidance:

- [Incident Response](references/incident-response.md) - Troubleshooting and incident management workflows. Load when responding to production incidents, investigating outages, or performing root cause analysis.

- [Log Analysis](references/log-analysis.md) - CloudWatch Logs Insights query patterns and syntax. Load when querying logs, extracting structured data, or aggregating log data.

- [Alerting Setup](references/alerting-setup.md) - Creating intelligent CloudWatch alarms with recommended configurations. Load when setting up new alarms, reducing alarm fatigue, or implementing SLO-based alerting.

- [Performance Monitoring](references/performance-monitoring.md) - Application Signals APM, service health, and distributed tracing. Load when monitoring microservices, analyzing traces, setting up SLOs, or investigating latency issues.

- [Security Auditing](references/security-auditing.md) - CloudTrail security analysis and compliance. Load when investigating security incidents, tracking API activity, performing compliance audits, or monitoring IAM changes.

- [Observability Gap Analysis](references/observability-gap-analysis.md) - Codebase analysis for observability best practices. Load when auditing codebases for missing instrumentation, logging gaps, or tracing coverage.

- [Application Signals Setup](references/application-signals-setup.md) - Step-by-step Application Signals enablement guide. Load when setting up Application Signals for the first time.

- [CloudTrail Data Source Selection](references/cloudtrail-data-source-selection.md) - CloudTrail data source priority and selection strategy. Referenced by security-auditing.md; not typically loaded directly.

## Quick Start Examples

### Investigate High Error Rate

1. Check active alarms and Application Signals for service health
2. Query CloudWatch Logs for error patterns and stack traces
3. Review CloudTrail for recent deployments or configuration changes
4. Analyze traces for root cause and dependency bottlenecks
5. Check AWS Documentation for error codes and troubleshooting

### Performance Optimization

1. Analyze CloudWatch Metrics for CPU, memory, and latency trends
2. Query Application Signals for P95/P99 latency and SLO compliance
3. Examine logs for slow operations and outliers

### Security Audit

1. Query CloudTrail for IAM changes and unauthorized access attempts
2. Correlate CloudTrail events with application logs
3. Check Application Signals for unusual traffic patterns

### Codebase Observability Audit

1. Analyze codebase structure and identify entry points
2. Assess logging coverage, structured logging, and correlation IDs
3. Evaluate metrics instrumentation and tracing implementation
4. Generate prioritized gap report with code examples

## Essential Log Query Patterns

### Basic Error Search

```
fields @timestamp, @message, @logStream, level
| filter level = "ERROR"
| sort @timestamp desc
| limit 100
```

### Performance Analysis

```
stats count() as requestCount,
      avg(duration) as avgDuration,
      pct(duration, 95) as p95Duration,
      pct(duration, 99) as p99Duration
by endpoint
| filter requestCount > 10
| sort p95Duration desc
| limit 100
```

### Error Rate Over Time

```
stats count() as total,
      sum(statusCode >= 500) as errors,
      (sum(statusCode >= 500) / count()) * 100 as errorRate
by bin(5m) as timeWindow
| sort timeWindow
```

## MCP Servers

| Server                                             | Purpose                                              |
| -------------------------------------------------- | ---------------------------------------------------- |
| `awslabs.cloudwatch-mcp-server`                    | CloudWatch Logs, Metrics, Alarms, log group analysis |
| `awslabs.cloudwatch-applicationsignals-mcp-server` | Application Signals APM, SLOs, distributed tracing   |
| `awslabs.cloudtrail-mcp-server`                    | CloudTrail security auditing, API activity tracking  |
| `awslabs.aws-documentation-mcp-server`             | Official AWS documentation search and access         |

## Best Practices

- **Logs**: Always include timestamp filters, use LIMIT, use `analyze_log_group` for automated pattern detection
- **Metrics**: Use Sum for count metrics, Average for utilization, percentiles for latency
- **Application Signals**: Start with `audit_services` using wildcard targets, use `search_transaction_spans` for 100% trace visibility
- **CloudTrail**: Follow data source priority (Lake > CloudWatch Logs > Lookup Events API)
- **Alarms**: Use recommended configurations, implement composite alarms, tune to reduce false positives
