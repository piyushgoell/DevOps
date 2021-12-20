# Infrastructure Monitoring

node exporter : system matrix for Prometheus (Linux) server.
windows exporter : system matrix for windows 

An exporter gathers metrics and create the endpoint that Promotheus can scrape.

## Node Exporter

    # CPU Matrics
    sudo apt-get install stress
    stress -m 2 [stress on memory with 2 virtual memory loads]
    
    # Memory Matrics
    stress -c 5 [stress on CPU with 5 loads]

    # Disk Matrics
    sudo apt-get install sysstat -y
    iostat

    # File System metrics


    # Networking Metrics


    # Load Metrics

    # Using cAdviser to Monitor Containers


# Application Monitoring
 
## Using Client Library

## Counters

## Gauges

## Summaries and Histograms

# Managing Alerts

## Recording Rules

## Alerting Rules


# Visualization