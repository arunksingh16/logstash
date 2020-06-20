# Logstash practical 101

Logstash is an open source data collection engine with real-time pipelining capabilities.

  - install and configure filebeat 
  - update logstash to receive input from filebeat
  - Magic
  
> Every configuration file is split into 3 sections, input, filter and output. They’re the 3 stages of most if not all ETL processes.
> 

# filebeat
```
curl -L -O https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-7.8.0-linux-x86_64.tar.gz
tar xzvf filebeat-7.8.0-linux-x86_64.tar.gz
# running filebeat
sudo ./filebeat -e -c filebeat.yml -d "publish" -strict.perms=false

```
# apache

```
sudo apt update
sudo apt install apache2
```

> updated the files as per blog https://medium.com/@arunksingh16/deploying-elk-stack-for-apache-logs-analysis-283d0b222c24


### Logstash Config can be managed via values.yaml or using configmaps

```
kubectl create configmap apache-pipeline --from-file apache-es.conf
```
