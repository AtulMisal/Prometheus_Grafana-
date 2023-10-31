# You can install Grafana in multiple ways as listed below :
    1. Using Helm charts
    2. Using Docker containers
    3. Using official commands listed on Prometheus Documentation.

    1. Using Helm charts
        1. Add helm repo
           helm repo add grafana https://grafana.github.io/helm-charts
        2. Update helm repo
           helm repo update
        3. Install helm
           helm install grafana grafana/grafana
        4. Expose Grafana Service
           kubectl expose service grafana — type=NodePort — target-port=3000 — name=grafana-ext

    2. Using Docker containers :
        docker run -d -p 3000:3000 --name=grafana grafana/grafana-enterprise

    3. Using official commands listed on Prometheus Documentation.
       1. sudo apt-get install -y apt-transport-https software-properties-common wget
       2. sudo mkdir -p /etc/apt/keyrings/
         wget -q -O - https://apt.grafana.com/gpg.key | gpg --dearmor | sudo tee /etc/apt/keyrings/grafana.gpg > /dev/null
       3. echo "deb [signed-by=/etc/apt/keyrings/grafana.gpg] https://apt.grafana.com stable main" | sudo tee -a /etc/apt/sources.list.d/grafana.list
       4. echo "deb [signed-by=/etc/apt/keyrings/grafana.gpg] https://apt.grafana.com beta main" | sudo tee -a /etc/apt/sources.list.d/grafana.list
       5. sudo apt-get update
       6. sudo apt-get install grafana
       7. sudo apt-get install grafana-enterprise

       http://localhost:3000
