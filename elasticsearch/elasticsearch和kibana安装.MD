1.elasticsearch.yml

cluster.name: "elasticsearch"
network.host: 0.0.0.0
http.cors.enabled: true
http.cors.allow-origin: "*"
xpack.security.enabled: true
xpack.license.self_generated.type: basic
xpack.security.transport.ssl.enabled: true

注意:
 1.1 /usr/local/src/elasticsearch/data 所有要赋予 777
 1.2 设置密码:
 	 docker exec -it elasticsearch /bin/bash
 	 ./bin/elasticsearch-setup-passwords auto
 	 记住要修改kibanal.yml 的配置es密码(elasticsearch.password)

2.kibanal.yml

server.name: kibana
server.host: "0"
elasticsearch.hosts: [ "http://192.168.40.110:9200" ]
xpack.monitoring.ui.container.elasticsearch.enabled: true
i18n.locale: zh-CN
elasticsearch.username: "elastic"
elasticsearch.password: "Fdrloq7W2sDVMezTYeVZ"