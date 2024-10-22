ansible-elasticsearch使用说明
=================


### 一、摘要

    本roles是针对es 7.x
    本roles适用于centos7.9


### 二、快速安装es集群

    ansible-playbook -i hosts.ini deploy_es.yml

    -i 这个选项指定了一个清单文件
    deploy_es.yml 这是要执行的Ansible剧本的文件名。该剧本包含了部署Elasticsearch集群所需的所有任务和配置
    

    


### 三、注意事项

>  变量注意事项

    ansible-elasticsearch/inventory 这个文件定义的角色ip，按照需求更改

    ansible-elasticsearch/group_vars/all.yml 这个文件定义了es的版本和java的版本

    ansible-elasticsearch/templates/elasticsearch.yml.j2 这个文件定义了es的配置文件但是没有加x-pack，按需更改

    






### 五、zk集群的状态检查

```cpp
curl命令直接向Elasticsearch的REST API发送请求，获取集群的状态信息
curl -X GET "http://<your-es-node>:9200/_cluster/health?pretty"

Elasticsearch还提供了监控API，可以获取更详细的集群和节点状态信息，这个命令将返回集群的统计信息，包括节点数量、索引数量、分片状态等
curl -X GET "http://<your-es-node>:9200/_cluster/stats?pretty"

检查节点状态
curl -X GET "http://<your-es-node>:9200/_cat/nodes?v"

```





### 六、注意事项

```cpp
    note: ansible version 2.3.2.0+
```
