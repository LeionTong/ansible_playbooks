## filebeat role 使用指南

### Variables：

    filebeat_version: 6.3.0
    filebeat_package: filebeat-{{ filebeat_version }}-linux-x86_64.tar.gz
    deploy_home: "{{ ansible_user_dir }}"
    install_path: "{{ deploy_home }}/filebeat"
    configuration_template: filebeat-input-log-ouput-kafka.yml.j2
    filebeat_inputs_enabled: true
    filebeat_inputs_paths: /opt/logstash-tutorial.log    # /var/log/*.log
    fields_log_topics: leion
    setup_kibana_host: "10.0.0.13:5601"
    output_logstash_hosts: '["10.0.0.13:5044"]'
    output_elasticsearch_hosts: '["10.0.0.11:9200", "10.0.0.12:9200"]'
    output_kafka_hosts: '["10.0.0.11:9092", "10.0.0.12:9092", "10.0.0.13:9092"]'

### Usage example:

#### filebeat_hosts：

    [filebeat_servers]
    10.0.0.11

#### filebeat.yml

    - hosts: filebeat_servers
      remote_user: deploy
      roles:
        - filebeat

#### Usage

`ansible-playbook -i filebeat_hosts filebeat.yml -u deploy`
