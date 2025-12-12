
[Main Menu](../README.md) | [Session 5](../session5/README.md) | [Exercise-5-1](../session5/Exercise-5-3.md)

## Exercise 5.3:  Compiling a MIB for data collection

## Compiling mibs using mib compiler

- [ ] Upload the MIBS from the `mibs` directory into the MIB compiler using the web interface, compile the MIBs in the correct dependency order
  - SNMPv2-SMI.mib
  - SNMPv2-TC.mib
  - UCD-SNMP-MIB.mib
- [ ] Generate a data collection configuration from the UCD-SNMP-MIB
- [ ] Investigate and discuss the generated configuration files and graph defintions (`datacollection/UCD-SNMP-MIB.xml` and `snmp-graph.properties.d/UCD-SNMP-MIB.properties`)

## Additional Performance topics

### Controlling data collections using filters

- [ ] Limit nodes from SNMP data collection based on a surveillance category `Collect-Enabled`

File: `etc/collectd-configuration.xml`
```xml
<package name="example1" remote="false">
  <filter>categoryName == 'Collect-Enabled'</filter>
  <include-range begin="1.1.1.1" end="254.254.254.254"/>
  <include-range begin="::1" end="ffff:ffff:ffff:ffff:ffff:ffff:ffff:ffff"/>
  ...
```

- [ ] Assign surveillance category `Collect-Enabled` to `linux-01 and verify the collection packages in the web user interface all three linux nodes
- [ ] Change the data collection frequency and how they relate to collection packages and RRD/JRobin files
- [ ] Assign node `linux-03` to the surveillance category `Collect-10s`
- [ ] Create a new collection set `default-10s` in the datacollection-config.xml, RRDTool and JRobin limitations
- [ ] Add a second SNMP collection package with the collection interval 10 sec instead of 5 min.

File: `etc/collectd-configuration.xml`
```xml
<package name="collect-10s" remote="false">
  <filter>categoryName == 'Collect-10s'</filter>
  <include-range begin="1.1.1.1" end="254.254.254.254"/>
  <include-range begin="::1" end="ffff:ffff:ffff:ffff:ffff:ffff:ffff:ffff"/>
  <service name="SNMP" interval="10000" user-defined="false" status="on">
    <parameter key="collection" value="default-10s"/>
    <parameter key="thresholding-enabled" value="true"/>
  </service>
</package>
```

IMPORTANT: To apply the settings Collectd needs a reload when a category was changed in the inventory

- [ ] Reload Collectd configuration with `ssh admin@localhost -p 8101 reload-daemon Collectd`
- [ ] It seems like we have a bug in 32.0.5 with the filter, as soon one filter applies for a node both collection packages are applied. Not sure if fixed in 33.x

### Thresholding

See [OpenNMS documentation on thresholds](https://docs.opennms.com/horizon/33/operation/deep-dive/thresholds/thresholding.html)

- [ ] Create a high threshold for CPU usage higher than 50%

![cpu-user-threshold.png](images/cpu-user-threshold.png)

- [ ] Install the `stress-ng` command on `linux-03` which can be used to simulate a high workload to trigger a threshold exceeded
      See [Stress-ng tutorial](https://www.cyberciti.biz/faq/stress-test-linux-unix-server-with-stress-ng/)

NOTE The linux SNMP containers are based on Centos 7.
As of 2024 Centos 7 is no longer maintained so we need the following commands to install the archive packages and get stress-ng from EPEL.

```
docker compose exec -u root linux-03 bash

# modify the default mirrors to point to new centos 7 vault address
sed -i 's/mirror\.centos\.org/vault.centos.org/g' /etc/yum.repos.d/CentOS-*.repo
sed -i 's/^#.*baseurl=http/baseurl=http/g' /etc/yum.repos.d/CentOS-*.repo
sed -i 's/^mirrorlist=http/#mirrorlist=http/g' /etc/yum.repos.d/CentOS-*.repo

yum install -y https://archives.fedoraproject.org/pub/archive/epel/7/x86_64/Packages/e/epel-release-7-14.noarch.rpm

yum install -y stress-ng

## running stress-ng in the container
stress-ng -c 1 -l 55 # Simulate ~55% CPU usage (ctrl c to exit)

```



