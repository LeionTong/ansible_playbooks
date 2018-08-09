## kafka role manual

### Variables：

    kafka_version: 2.12-1.1.0
    kafka_package: kafka_{{ kafka_version }}.tgz
    deploy_home: "{{ ansible_user_dir }}"
    install_path: "{{ deploy_home }}/kafka"
    kafka_manager_version: 1.3.0.6
    kafka_manager_package: "kafka-manager-{{ kafka_manager_version }}.tar.gz"
    kafka_manager_ip: 10.0.0.11
    listeners: "PLAINTEXT://{{ inventory_hostname }}:9092"
    num_network_threads: 3
    num_io_threads: 8
    log_dirs: /home/deploy/kafka/kafka-logs
    num_partitions: 8
    num_recovery_threads_per_data_dir: 1
    zookeeper_connect: 10.0.0.11:12181,10.0.0.12:12181,10.0.0.13:12181

### Usage example:

#### kafka_hosts：

    [kafka_servers]
    10.0.0.11 broker_id=0
    10.0.0.12 broker_id=1
    10.0.0.13 broker_id=2

#### kafka.yml

    - hosts: kafka_servers
      # remote_user: deploy
      roles:
        - kafka

#### Usage

`ansible-playbook -i kafka_hosts kafka.yml -u deploy`
