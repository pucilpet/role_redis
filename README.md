Ansible Role: redis
=========

本 Role 用于在Linux下安装 [redis](https://redis.io/) 和 [RedisInsight](https://redislabs.com/redisinsight/)。

## Requirements

运行本 Role，请确认符合如下的必要条件：

| **Items**      | **Details** |
| ------------------| ------------------|
| Operating system | CentOS7.x Ubuntu18.04 AmazonLinux |
| Python 版本 | Python2  |
| Python 组件 |    |
| Runtime |  |


## Related roles

本 Role 在运行时需要确保已经运行：common。以下为例：

```
roles:
    - {role: role_common, tags: "role_common"}
    - {role: role_redis, tags: "role_redis"}
```


## Variables

本 Role 主要变量以及使用方法如下：

| **Items**      | **Details** | **Format**  | **是否初始化** |
| ------------------| ------------------|-----|-----|
| redis_version | [ 2.8,3.0,3.2,4.0,5.0,stable ] | 字符串 | 否 |
| redis_install | True,False | 布尔 | 否 |
| redis_install_redisinsight | False, True| 布尔 | 否 |

## Example

```
- name: Redis
  hosts: all
  become: yes
  become_method: sudo 
  vars_files:
    - vars/main.yml 

  roles:
    - { role: role_common }
    - { role: role_redis }
    ...
```

## FAQ


