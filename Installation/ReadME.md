In DevOps we need to monitor diff things as 
  1. Metrics
  2. Logs
  3. Alerting
Prometheus is used when we have metrics data and it can be stored as time series database. It is ephimeral in nature (Means Short Lived Data), so to overcome this we can use Influx DB.

When we have to monitor logs Prometheus is not suited for these kind of tasks and here we can use Loki along with Promtail.

