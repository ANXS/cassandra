## Ansibles - cassandra [![Build Status](https://travis-ci.org/Ansibles/cassandra.png)](https://travis-ci.org/Ansibles/cassandra)

Ansible role which installs and configures Apache Cassandra.


#### Requirements & Dependencies

##### Ansible

It has been tested on Ansible 1.5 and above, and depends on the following roles:
  - Ansibles.oracle-jdk


#### Variables

```yaml
cassandra_install_method: "package"
...
```

Please, head over to the [defaults/main.yml](defaults/main.yml) file, to have a full view on the cassandra configuration options.

At this stage, I highly recommend using the package option, since it comes with a init script,
and I haven't found the time to make one for the source installation.


#### License

Licensed under the MIT License. See the LICENSE file for details.


#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/ansibles/cassandra/issues)!
