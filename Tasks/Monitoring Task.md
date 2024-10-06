## Task Description:

  1. Install Prometheus and Grafana on a Linux EC2 machine, connect Prometheus to Grafana, and create a dashboard to view metrics.

     - Instances for Node_Exporter, Prometheus and Grafana
    
       <img width="883" alt="image" src="https://github.com/user-attachments/assets/52bc01fc-c8ab-4124-8792-a4a0b30ca015">

     - Install Node-Exporter

       ```
       cd /opt/
       sudo wget https://github.com/prometheus/node_exporter/releases/download/v1.1.2/node_exporter-1.1.2.linux-amd64.tar.gz
       sudo tar xf node_exporter-1.1.2.linux-amd64.tar.gz
       sudo mv node_exporter-1.1.2.linux-amd64 node_ex porter
       cd node_exporter
       sudo ./node_exporter
       ```
       <img width="899" alt="image" src="https://github.com/user-attachments/assets/a6ffe781-b23f-47e3-9d3c-96a13649e705">
       <img width="957" alt="image" src="https://github.com/user-attachments/assets/446c5f9d-9abe-4c52-bbfa-40f9f26ed1d8">

     - Install Prometheus

        ```
        cd /opt/
        sudo wget https://github.com/prometheus/prometheus/releases/download/v2.26.0/prometheus-2.26.0.linux-amd64.tar.gz
        sudo tar xf prometheus-2.26.0.linux-amd64.tar.gz
        sudo mv prometheus-2.26.0.linux-amd64 prometheus
        cd prometheus/
        sudo vi prometheus.yml
        sudo ./prometheus  
        ```
        prometheus.yml

        ```
        global:
        scrape_interval:     15s
          evaluation_interval: 15s 
        
        alerting:
          alertmanagers:
          - static_configs:
            - targets:
        
        scrape_configs:
          - job_name: 'prometheus'
            static_configs:
              - targets: ['localhost:9090',172.31.7.113:9100]
        ```
        <img width="958" alt="image" src="https://github.com/user-attachments/assets/e9ff3a9c-6036-42cf-96db-88905a2c2eb3">

     - Install Grafana

        ```
          sudo vi /etc/yum.repos.d/grafana.repo
        ```
        ```
        [grafana]
        name=grafana
        baseurl=https://packages.grafana.com/oss/rpm
        repo_gpgcheck=1
        enabled=1
        gpgcheck=1
        gpgkey=https://packages.grafana.com/gpg.key
        sslverify=1
        sslcacert=/etc/pki/tls/certs/ca-bundle.crt
        ```
        ```
        sudo yum install Grafana
        sudo systemctl start grafana-server
        sudo systemctl enable grafana-server
        ```
       <img width="959" alt="image" src="https://github.com/user-attachments/assets/b5ca1f8d-4098-4509-b109-c2e38ae970e0">
       <img width="934" alt="image" src="https://github.com/user-attachments/assets/127947cb-8f41-4a8f-8ab2-9a01b247975d">
       <img width="958" alt="image" src="https://github.com/user-attachments/assets/6afc41d7-2407-416d-bc64-dbe1260a199e">

       ___
