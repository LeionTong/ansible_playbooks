## kibana role 使用指南

### Variables：

    kibana_version: 6.3.0
    kibana_package: kibana-{{ kibana_version }}-linux-x86_64.tar.gz
    deploy_home: "{{ ansible_user_dir }}"
    install_path: "{{ deploy_home }}/kibana"
    server_port: 5601
    server_host: "10.0.0.13"
    server_name: "leion's kibana"
    elasticsearch_url: "http://10.0.0.11:9200"

### Usage example:

#### kibana_hosts：

    [kibana_servers]
    10.0.0.13


#### kibana.yml

    - hosts: kibana_servers
      remote_user: deploy
      roles:
        - kibana

#### Usage

`ansible-playbook -i kibana_hosts kibana.yml -u deploy`
