## logstash role 使用指南

### Variables：

    logstash_version: 6.3.0
    logstash_package: logstash-{{ logstash_version }}.tar.gz
    deploy_home: "{{ ansible_user_dir }}"
    install_path: "{{ deploy_home }}/logstash"
    path_data: "{{ install_path }}/data"
    path_logs: "{{ install_path }}/logs"
    logstash_pipeline_conf: logstash-input-file-output-stdout.conf

### Usage example:

#### logstash_hosts：

    [logstash_servers]
    10.0.0.13

#### logstash.yml

    - hosts: logstash_servers
      remote_user: deploy
      roles:
        - logstash

#### Usage

`ansible-playbook -i logstash_hosts logstash.yml -u deploy`
