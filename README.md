# Nagios plugins

### Prerequisites 
- Python3
- boto3 extention (using: pip install boto3)
- AWS cli [installed](https://docs.aws.amazon.com/cli/latest/userguide/installing.html)
- AWS Access key, Secret key and Region [configured](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html)

## AWS ECS Cluster conatiners counter
### ecs_ps_count.py
### Objective 
- Get running containers counter of ECS Cluster.

### Usage 
```
./ecs_ps_count.py [-h] [--clustername CLUSTERNAME] [--ok_threshold OK_THRESHOLD] [--critical_threshold CRITICAL_THRESHOLD]
```

### Arguments  

`-h, --help`  
  Show this help message and exit  
  
`--clustername CLUSTERNAME`  
Classic Load Balancer provides basic load balancing across multiple Amazon EC2 instances and operates at both the request level and connection level.

`--ok_threshold OK_THRESHOLD`  
Threshold which reflects the OK status value. (For Example: 2)

`--critical_threshold CRITICAL_THRESHOLD`  
Threshold which reflects the Critical status value. (For Example: 2)

## AWS Classic Load Balancer unhealthy check
### clb_unhealthyCheck.py
### Objective 
- Get metric of [AWS CLB](https://aws.amazon.com/elasticloadbalancing/details/#details) UnHealthyHostCount.
- This plugin exist & approved by [Nagios Exchange](https://exchange.nagios.org/directory/Plugins/Cloud/AWS-Classic-Load-Balancer-unhealthy-check/details).

### Usage 
```
./clb_unhealthyCheck.py [-h] [--loadbalancer LOADBALANCER] [--period PERIOD] [--statistics STATISTICS]
                     [--unit UNIT] [--ok_threshold OK_THRESHOLD] [--critical_threshold CRITICAL_THRESHOLD]
```

### Arguments  

`-h, --help`  
  Show this help message and exit  
  
`--loadbalancer LOADBALANCER`  
Classic Load Balancer provides basic load balancing across multiple Amazon EC2 instances and operates at both the request level and connection level.
For example: awseb-e-m-AWSEBLoa-Numbers&Characters
          
`--period PERIOD `  
A period is the length of time associated with a specific Amazon CloudWatch statistic.  
For example: to specify a period of 5 minutes, use 300 as the period value.  
                        
`--statistics STATISTICS`  
Statistics are metric data aggregations over specified periods of time.  
For example: Average  
                        
`--unit UNIT`  
Each statistic has a unit of measure.  
For example: Count  

`--ok_threshold OK_THRESHOLD`  
Threshold which reflects the OK status value. (Recommended threshold: 0)

`--critical_threshold CRITICAL_THRESHOLD`  
Threshold which reflects the Critical status value. (Recommended threshold: 0)

## AWS Application Load Balancer unhealthy check
### alb_unhealthyCheck.py
### Objective 
- Get metric of [AWS ALB](https://aws.amazon.com/elasticloadbalancing/details/#details) UnHealthyHostCount.
- This plugin exist & approved by [Nagios Exchange](https://exchange.nagios.org/directory/Plugins/Cloud/AWS-Application-Load-Balancer-unhealthy-check/details).

### Usage 
```
./alb_unhealthyCheck.py [-h] [--targetgroup TARGETGROUP] [--loadbalancer LOADBALANCER] [--period PERIOD] [--statistics STATISTICS]
                     [--unit UNIT] [--ok_threshold OK_THRESHOLD] [--critical_threshold CRITICAL_THRESHOLD]
```

### Arguments  

`-h, --help`  
  Show this help message and exit  
  
`--targetgroup TARGETGROUP`  
Each target group is used to route requests to one or more registered targets.
For example: targetgroup/target-group-name/numbers&characters

`--loadbalancer LOADBALANCER`  
The load balancer distributes incoming application traffic across multiple targets.
For example: app/application-load-balancer/numbers&characters
          
`--period PERIOD `  
A period is the length of time associated with a specific Amazon CloudWatch statistic.  
For example: to specify a period of 5 minutes, use 300 as the period value.  
                        
`--statistics STATISTICS`  
Statistics are metric data aggregations over specified periods of time.  
For example: Average  
                        
`--unit UNIT`  
Each statistic has a unit of measure.  
For example: Count  

`--ok_threshold OK_THRESHOLD`  
Threshold which reflects the OK status value. (Recommended threshold: 0)

`--critical_threshold CRITICAL_THRESHOLD`  
Threshold which reflects the Critical status value. (Recommended threshold: 0)

## AWS ECS service monitor
### ecs_service_memory_cpu.py
### Objective 
- Get metrics of [AWS ECS](https://aws.amazon.com/ecs/) service Memory & CPU.
- This plugin exist & approved by [Nagios Exchange](https://exchange.nagios.org/directory/Plugins/Cloud/ECS-cluster-and-service-monitor/details).

### Usage 
```
./ecs_service_memory_cpu.py [-h] [--namespace NAMESPACE] [--metricname METRICNAME] [--clustername CLUSTERNAME]
                     [--servicename SERVICENAME] [--period PERIOD] [--statistics STATISTICS]
                     [--unit UNIT] [--ok_threshold OK_THRESHOLD] [--warning_threshold WARNING_THRESHOLD]
                     [--critical_threshold CRITICAL_THRESHOLD]
```

### Arguments  

`-h, --help`  
  Show this help message and exit  
  
`--namespace NAMESPACE`  
CloudWatch namespaces are containers for metrics.  
For example: AWS/ECS  

`--metricname METRICNAME`  
Metrics are data about the performance of your systems.  
For example: MemoryUtilization  

`--clustername CLUSTERNAME`  
This dimension filters the data you request for all resources in a specified cluster.

`--servicename SERVICENAME`  
This dimension filters the data you request for all resources in a specified service within a specified cluster.
          
`--period PERIOD `  
A period is the length of time associated with a specific Amazon CloudWatch statistic.  
For example: to specify a period of 5 minutes, use 300 as the period value.  
                        
`--statistics STATISTICS`  
Statistics are metric data aggregations over specified periods of time.  
For example: Average  
                        
`--unit UNIT`  
Each statistic has a unit of measure.  
For example: Percent  

`--ok_threshold OK_THRESHOLD`  
Threshold which reflects the OK status value. (Recommended threshold: 86)

`--warning_threshold WARNING_THRESHOLD`  
Threshold which reflects the Warning status value. (Recommended threshold: 86)

`--critical_threshold CRITICAL_THRESHOLD`  
Threshold which reflects the Critical status value. (Recommended threshold: 96)

## AWS ECS cluster monitor
### ecs_cluster_memory_cpu.py
### Objective 
- Get metrics of [AWS ECS](https://aws.amazon.com/ecs/) cluster Memory & CPU.

### Usage 
```
./ecs_cluster_memory_cpu.py [-h] [--namespace NAMESPACE] [--metricname METRICNAME] [--clustername CLUSTERNAME]
                     [--servicename SERVICENAME] [--period PERIOD] [--statistics STATISTICS]
                     [--unit UNIT] [--ok_threshold OK_THRESHOLD] [--warning_threshold WARNING_THRESHOLD]
                     [--critical_threshold CRITICAL_THRESHOLD]
```

### Arguments  

`-h, --help`  
  Show this help message and exit  
  
`--namespace NAMESPACE`  
CloudWatch namespaces are containers for metrics.  
For example: AWS/ECS  

`--metricname METRICNAME`  
Metrics are data about the performance of your systems.  
For example: MemoryUtilization  

`--clustername CLUSTERNAME`  
This dimension filters the data you request for all resources in a specified cluster.
          
`--period PERIOD `  
A period is the length of time associated with a specific Amazon CloudWatch statistic.  
For example: to specify a period of 5 minutes, use 300 as the period value.  
                        
`--statistics STATISTICS`  
Statistics are metric data aggregations over specified periods of time.  
For example: Average  
                        
`--unit UNIT`  
Each statistic has a unit of measure.  
For example: Percent  

`--ok_threshold OK_THRESHOLD`  
Threshold which reflects the OK status value. (Recommended threshold: 70)

`--warning_threshold WARNING_THRESHOLD`  
Threshold which reflects the Warning status value. (Recommended threshold: 70)

`--critical_threshold CRITICAL_THRESHOLD`  
Threshold which reflects the Critical status value. (Recommended threshold: 80)
