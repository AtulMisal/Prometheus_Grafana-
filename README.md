
# Here we will learn Prometheus & Grafana.

# Prometheus, Grafana & Loki :
    Prometheus : Matrics monitoring as well as works as pull based tool.
    Loki : log aggregation tool
  
    Grafana is an tool which provides data in visuals so prometheus & loki are using grafana to display the data.

    As a DevOps engineer we deploy our app on server but along with this we have to monitor , collect the logs, 
    sending alerts when needed.
   
    But in case of logging Prometheus is not a best tool it is used when we have time series data/metrics but to collect loges we are 
    using Loki. It works as datasource to Grafana.
  
    To collect logs from diff server we use Promtail and it provide to Loki.

    Loki and Prometheus are both open source tools. While Loki is a log aggregation tool, Prometheus is a metrics monitoring tool. Loki's 
    design is inspired by Prometheus but for logs.

    Grafana <-- Loki <-- Promtail    
 
    Prometheus works as a datasource for Grafana as Grafana is a visualization platform.
    Here developers will create the metrics server and we can use it in Prometheus and as we configured it in Grafana will get the 
    dashboard.
 
    Features :
       1. Its highly scalable and available.
       2. It has minimal external dependencies.
       3. Deployment is easy.  
	     4. A multi-dimensional data model
  
    Prometheus Components:
       1. Prometheus server: This is the main component which scrapes and also stores time series data (Stores data with 
	     timestamp. The time series data can be accessed via http server.

       2. Client libraries: Before we can monitor our services, we need to add instrumentation to the application 
	     code using one of the Prometheus client libraries. 

       3. Push Gateway: For short-lived jobs like small scripts which executes within seconds we can use push 
	      gateway to get metrics.

       4. Exporters: Exporters are used to generate metrics in Prometheus format. 

       5. Alert Manager: In order to handle alerts. 

 
    Metric:
       Metric is a value of a quantity at a given point of time. 
 
    Basic Metric Types:
       Counter: 
         It is a metric whose value increases during the lifetime of a process/system.
	       Also records the values that only goes up.
         For example, you can represent the number of logs generated, requests served, processes completed, or errors.
   
       Gauge: 
         It is metric whose value can go up or down arbitrarily.
         For example, you can represent the current CPU usage, memory usage or temperature.
   
       Histogram: 
         It is metric that samples observations and then counts them in configurable buckets. It also provides 
         a sum of all observed values. It helps to measure data like "how long something took?" or "how big a particular 
         request was?".
         For example, request durations, or number of children's in different age groups.

       Summaries:
	       Take many measurments of value to later calculate the avg.
		 
		 
      PromQL:
        It is Prometheus’s own query language that used for retrieving data from the Prometheus server. 

![prom](https://github.com/AtulMisal/Prometheus_Grafana-/assets/108976232/5bb8da3f-61d2-4d5c-8d0f-10a10a1bca0c)
