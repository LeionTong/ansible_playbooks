## zookeeper role manual

### Variables：

    zookeeper_version: 3.4.12
    zookeeper_package: zookeeper-{{ zookeeper_version }}.tar.gz
    install_path: /home/deploy/zookeeper
    tickTime: 2000
    initLimit: 10
    syncLimit: 5
    dataDir: /home/deploy/zookeeper/zkdata
    clientPort: 12181
    dataLogDir: /home/deploy/zookeeper/zkdatalog
    server_1: 10.0.0.11:12888:13888
    server_2: 10.0.0.12:12888:13888
    server_3: 10.0.0.13:12888:13888


### Usage example:

#### zookeeper_hosts：
    [zookeeper_servers]
    10.0.0.11:22 myid=1
    10.0.0.12:22 myid=2
    10.0.0.13:22 myid=3

#### zookeeper.yml
    - hosts: zookeeper_servers
      remote_user: deploy
      roles:
      - zookeeper

#### Usage

`ansible-playbook -i zookeeper_hosts zookeeper.yml -u deploy`
