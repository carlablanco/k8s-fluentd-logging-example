# k8s-fluentd-logging-example

Replicates sending Application Logs from Kubernetes on-prem cluster using Sidecar Fluentd to BigQuery.

Steps:
1. Set up the fluent.conf
2. Create the Dockerfile
3. Build the Docker image with Build and Push commands
4. Deploy to GKE on desired cluster --> Fluentd runs as a Daemonset (works for every single pod). 

Docker:
Used v.2.2 (last) with Debian 1.4 because 1.15 (last) wasn't working - compatibility issue maybe?
Hardcoded ruby gem (activesupport) - compatibility issues again.
Rest is documentation

Config:
Readme of the plugin, full documentation.
Minimum of fluentd: source (tailgate of whichever file, np)

WARNING:
We could use a buffer for writing to BQ, but will we hit a limit anyway? 
Logs are high rate event per se.... so....


https://docs.fluentd.org/v/0.12/articles/kubernetes-fluentd
https://github.com/fluent-plugins-nursery/fluent-plugin-bigquery#configuration
