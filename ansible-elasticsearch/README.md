zk_cluster使用说明
=================


### 一、摘要

    本roles是针对zk 3.4.8
    本roles适用于centos6


### 二、快速安装zookeeper cluster版本

    ansible-playbook -i hlist zk_cluster.yml -uroot -k -vv

    -u 指定远程主机执行脚本的账号
    -k 指定上面对应账号的密码
    -vv 显示执行过程中的详情

    Note: 如果做了公钥认证的话，可以使用下面的执行方式

    ansible-playbook -i hlist zk_cluster.yml -vv


### 三、注意事项

>  变量注意事项

    使用之前一定要修改hlist中的IP为你所需要部署服务的远程机器的IP

    如果场景不同，clone该代码仓库之后，请自行修改../vars/mail.yml中的相关信息来满足当前场景的需求


> 变量参考

```cpp
java:
  - java-1.8.0-openjdk
  - java-1.8.0-openjdk-devel
  - java-1.8.0-openjdk-headless


```


### 四、Ansible获取系统信息样例


> 示范如下

```cpp
    获取myid
    for语句遍历vars下的zookeeper_hosts字典,见myid.j2模板
    

    获取zoo.cfg中的server配置,见zoo.cfg.j2中的for语句


```



### 五、zk使用

```cpp
/etc/init.d/zookeeper Usage: /etc/init.d/zookeeper {start|stop|status|sstatus|restart|condrestart}

启动命令：/etc/init.d/zookeeper start 关闭命令：/etc/init.d/zookeeper stop 查看状态命令：/etc/init.d/zookeeper sstatus 客户端命令：zkCli.sh -server localhost:2181
```



### 六、下载zookeeper安装包

```cpp
    wget http://archive.apache.org/dist/zookeeper/zookeeper-3.4.8/zookeeper-3.4.8.tar.gz
```

### 七、注意事项

```cpp
    note: ansible version 2.3.2.0+
```
