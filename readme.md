Нужен mongo 3.2
```
deb http://repo.mongodb.org/apt/ubuntu trusty/mongodb-org/3.2 multiverse >> /etc/apt/sources.list.d/mongo.list
```

 nano /etc/systemd/system/mongo.service
```
[Unit]
Description=High-performance, schema-free document-oriented database
After=network.target
Documentation=https://docs.mongodb.org/manual

[Service]
#User=mongodb
#Group=mongodb
ExecStart=/usr/bin/mongod --quiet --config /etc/mongod.conf
LimitFSIZE=infinity
# (cpu time)
LimitCPU=infinity
# (virtual memory size)
LimitAS=infinity
# (open files)
LimitNOFILE=64000
# (processes/threads)
LimitNPROC=64000
Restart=always
[Install]
WantedBy=multi-user.target


```
