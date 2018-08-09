## jdk8 role 使用指南

### Variables：

    jdk_package: jdk-8u171-linux-x64.tar.gz
    jdk_version: 1.8.0_171
    install_path: /home/deploy/java
    env_file: /etc/profile.d/java_env.sh

### Usage example:

#### jdk8_hosts：

    [jdk_servers]
    10.0.0.11
    10.0.0.12
    10.0.0.13

#### jdk8.yml

    - hosts: jdk_servers
      remote_user: deploy
      roles:
      - jdk8

#### Usage

`ansible-playbook -i jdk8_hosts jdk8.yml -u deploy`
