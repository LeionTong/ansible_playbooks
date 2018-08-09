# ansible_playbooks

ELKB roles playbook：

Data Source => filebeat => Kafka <=> zookeeper
                  ||
                  ︾
               logstash => Elasticsearch => Kibana
                  ||
                  ︾ => => hdfs

For comprehensive details refer to the README.md in every role directory.
