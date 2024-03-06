# prometh_graf

https://ibrahims.medium.com/how-to-install-prometheus-and-grafana-on-ubuntu-22-04-lts-configure-grafana-dashboard-5d11e3cb3cfd

https://www.cherryservers.com/blog/install-prometheus-ubuntu

https://prometheus.io/docs/prometheus/latest/getting_started/

# History

```
  368  sudo nano /etc/systemd/system/prometheus.service
  369  sudo groupadd --system prometheus
  370  sudo useradd -s /sbin/nologin --system -g prometheus prometheus
  371  sudo mkdir /etc/prometheus
  372  sudo mkdir /var/lib/prometheus
  373  wget https://github.com/prometheus/prometheus/releases/download/v2.43.0/prometheus-2.43.0.linux-amd64.tar.gz
  374  tar vxf prometheus*.tar.gz
  375  cd prometheus*/
  376  sudo mv prometheus /usr/local/bin
  377  sudo mv promtool /usr/local/bin
  378  sudo chown prometheus:prometheus /usr/local/bin/prometheus
  379  sudo chown prometheus:prometheus /usr/local/bin/promtool
  380  sudo mv prometheus /usr/local/bin
  381  sudo mv promtool /usr/local/bin
  382  sudo chown prometheus:prometheus /usr/local/bin/prometheus
  383  sudo chown prometheus:prometheus /usr/local/bin/promtool
  384  sudo mv consoles /etc/prometheus
  385  sudo mv console_libraries /etc/prometheus
  386  sudo mv prometheus.yml /etc/prometheus
  387  sudo chown prometheus:prometheus /etc/prometheus
  388  sudo chown -R prometheus:prometheus /etc/prometheus/consoles
  389  sudo chown -R prometheus:prometheus /etc/prometheus/console_libraries
  390  sudo chown -R prometheus:prometheus /var/lib/prometheus
  391  sudo nano /etc/prometheus/prometheus.yml
  392  sudo vim /etc/systemd/system/prometheus.service
  393  sudo systemctl daemon-reload
  394  sudo systemctl enable prometheus
  395  sudo systemctl start prometheus
  396  sudo systemctl status prometheus
  397  sudo ufw allow 9090/tcp
  398  sudo apt update -y && sudo apt upgrade -y
  399  sudo apt install -y apt-transport-https software-properties-common wget
  400  sudo mkdir -p /etc/apt/keyrings/
  401  wget -q -O - https://apt.grafana.com/gpg.key | gpg --dearmor | sudo tee /etc/apt/keyrings/grafana.gpg > /dev/null
  402  sudo apt install -y apt-transport-https software-properties-common wget
  403  sudo mkdir -p /etc/apt/keyrings/
  404  wget -q -O - https://apt.grafana.com/gpg.key | gpg --dearmor | sudo tee /etc/apt/keyrings/grafana.gpg > /dev/null
  405  echo "deb [arch=amd64 signed-by=/etc/apt/keyrings/grafana.gpg] https://apt.grafana.com stable main" | sudo tee -a /etc/apt/sources.list.d/grafana.list
  406  sudo apt update
  407  sudo apt install grafana
  408  sudo systemctl start grafana-server
  409  sudo systemctl enable grafana-server
  410  sudo systemctl status grafana-server --no-pager -l
  411  sudo ufw allow 3000/tcp
  412  sudo systemctl status prometheus

```

# screens

```
http://localhost:3000/connections/datasources/edit/b58de004-bab9-4f86-811b-cd730f2885c3
```

![image](https://github.com/kode2go/prometh_graf/assets/29664888/2ee8bdcf-feb9-41f1-927c-2db4a8b49322)

![image](https://github.com/kode2go/prometh_graf/assets/29664888/e4a45bd8-5eeb-4ac9-9c76-c4c5405631a4)

```
http://localhost:3000/dashboard/new?orgId=1&from=1708360726578&to=1708360771404
```

![image](https://github.com/kode2go/prometh_graf/assets/29664888/d511c3b5-ba29-4d65-8988-684d4418431a)

```
http://localhost:9090/graph?g0.expr=prometheus_target_interval_length_seconds&g0.tab=0&g0.stacked=0&g0.show_exemplars=0&g0.range_input=1h&g1.expr=process_virtual_memory_bytes&g1.tab=0&g1.stacked=0&g1.show_exemplars=0&g1.range_input=1h
```

![image](https://github.com/kode2go/prometh_graf/assets/29664888/95b100e8-bfc3-4e67-8234-f27ff3eca8e6)


