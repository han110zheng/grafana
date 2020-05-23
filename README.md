## alertmanager  告警模块
https://prometheus.io/download/

## node-exporter Linux操作系统采集（如CPU，内存，硬盘，网络等）
https://prometheus.io/download/

## wmi_exporter Windows操作系统采集（如CPU，内存，硬盘，网络等）
https://github.com/martinlindhe/wmi_exporter/releases

## cadvisor 容器监控
https://axibase.com/products/axibase-time-series-database/writing-data/docker-cadvisor/

## Prometheus 采集数据
https://prometheus.io/download/

## mysql，windwos 监控

## 集成zabbix
https://github.com/alexanderzobnin/grafana-zabbix

https://alexanderzobnin.github.io/grafana-zabbix/installation/

## Docker环境依赖安装
yum install -y yum-utils device-mapper-persistent-data lvm2 git vim net-tools

## 安装containerd
yum  install -y https://download.docker.com/linux/centos/7/x86_64/stable/Packages/containerd.io-1.2.6-3.3.el7.x86_64.rpm

## 安装 docker-ce-cli
yum install -y https://download.docker.com/linux/centos/7/x86_64/stable/Packages/docker-ce-cli-19.03.8-3.el7.x86_64.rpm

## 安装 docker-ce
yum install -y https://download.docker.com/linux/centos/7/x86_64/stable/Packages/docker-ce-19.03.8-3.el7.x86_64.rpm

## 启动 docker
systemctl enable --now docker

## 查看安装版本
docker --version
#Docker version 19.03.8, build afacb8b

## 安装Docker Compose
curl -L "https://github.com/docker/compose/releases/download/1.25.5/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

## 如果docker-compose命令在安装后失败，请检查路径。您还可以创建到/usr/bin或路径中的任何其他目录的符号链接
ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose

## 查看Docker Compose版本是否安装
docker-compose --version

## 创建网络
docker network create --driver=bridge --subnet=172.22.0.0/16 grafana

## 执行Prometheus+Grafana安装
docker-compose up -d

## 查看容器
docker ps -a 或者 docker-compose ps -a

## grafana安装zabbix插件
docker exec -it grafana grafana-cli plugins install alexanderzobnin-zabbix-app

## 重启grafana
docker restart grafana
