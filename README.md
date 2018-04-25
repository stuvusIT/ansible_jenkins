# jenkins

This role installs Jenkins and configures the start parameters.

## Requirements

Ubuntu

## Role Variables

| Name                | Default / Mandatory                 | Description                                          |
|:--------------------|:-----------------------------------:|:-----------------------------------------------------|
| `jenkins_java`      | `/usr/bin/java`                     | Path to the Java installation Jenkins should execute |
| `jenkins_java_args` | `-Djava.awt.headless=true`          | Additional arguments to pass to the JVM              |
| `jenkins_pidfile`   | `/var/run/jenkins/jenkins.pid`      | Path to the PID file Jenkins should create on launch |
| `jenkins_user`      | `jenkins`                           | User under which Jenkins should run                  |
| `jenkins_group`     | `jenkins`                           | Group under which Jenkins should run                 |
| `jenkins_home`      | `/var/lib/jenkins`                  | Home directory of Jenkins                            |
| `jenkins_log`       | `daemon.info`                       | File or syslog log target                            |
| `jenkins_max_fd`    | `8192`                              | Maximum amount of open file handles for Jenkins      |
| `jenkins_umask`     | `027`                               | Umask for Jenkins                                    |
| `jenkins_http_host` | `0.0.0.0`                           | Host to bind on for HTTP connections                 |
| `jenkins_http_port` | `8080`                              | Port to bind on for HTTP connections                 |
| `jenkins_prefix`    | `/`                                 | Servlet context prefix for Jenkins                   |
| `jenkins_args`      | (See [defaults/main.yml](defaults)) | Start parameters for Jenkins                         |

## Example Playbook

```yml
- hosts: builders
  roles:
    - role: jenkins
      jenkins_log: /var/log/jenkins
      jenkins_host: 127.0.0.1
      jenkins_port: 8081
```

## License

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/).

## Author Information

- [Janne Heß](https://github.com/dasJ)
