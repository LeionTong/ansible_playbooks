## elasticsearch role manual

### Variables：

    es_version: 6.3.0
    es_package: elasticsearch-{{ es_version }}.tar.gz
    deploy_home: "{{ ansible_user_dir }}"
    install_path: "{{ deploy_home }}/elasticsearch"
    master_ip: 10.0.0.11
    cluster_name: es-cluster
    path_data: {{ install_path }}/data
    path_logs: {{ install_path }}/logs
    bootstrap_memory_lock: false
    ES_MEM: 2g
    network_host: "{{ ansible_eth1.ipv4.address }}"
    http_port: 9200
    discovery_zen_ping_unicast_hosts: '["10.0.0.11", "10.0.0.12"]'
    discovery_zen_minimum_master_nodes: 1
    gateway_recover_after_nodes: 2

### Usage example:

#### elasticsearchhosts：

    [elasticsearch_servers]
    10.0.0.11 node_name=es-node-1 node_master=true
    10.0.0.12 node_name=es-node-2 node_master=false

#### elasticsearch.yml

    - hosts: elasticsearch_servers
      remote_user: deploy
      roles:
        - elasticsearch

#### Usage

`ansible-playbook -i elasticsearch_hosts elasticsearch.yml -u deploy`
