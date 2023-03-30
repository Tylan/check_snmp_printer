# check_snmp_printer
Nagios and Icinga Plugin for Checking SNMP Printer Status (Trays, Consumables and Pagecounts) which includes PerfData.

## 2.0.0 POSSIBLE CODE BREAKING UPDATE

Must have Net-SNMP and its libraries installed.  Can be compiled from source from www.net-snmp.org (latest version) or via package managers:

Debian:
```
sudo apt-get install snmp
sudo apt-get install libsnmp-perl
```

Centos/RHEL:
```
sudo yum install net-snmp
sudo yum install net-snmp-utils
sudo yum install net-snmp-devel
sudo yum install net-snmp-perl
```

Supported Printer Models:

* Canon
* HP
* Xerox
* Ricoh
* Brother
* Lexmark
* Kyocera
* Olivetti

__Your specific printer not supported?  Open an issue on Github and we'll work to get it supported.__

Forked and modified from Franky Van Liedekerke's 2014 version.

**Consumables**

![](img/ConsumableCriticalGraph.png)

**Tray Status**

![](img/TrayStatusGraph.png)

**Page Count**

![](img/PagecountGraph.png)

## Getting Started

These instructions assume your Icinga2 is installed on a RHEL/CentOS system.  You may need to modify slightly to work with other systems.

### Prerequisites

Perl >= 5.10

Net-SNMP and Libraries:

Debian:
```
sudo apt-get install snmp
sudo apt-get install libsnmp-perl
```

Centos/RHEL:
```
sudo yum install net-snmp
sudo yum install net-snmp-utils
sudo yum install net-snmp-devel
sudo yum install net-snmp-perl
```

Nagios plugins installed and located in one of the following directories:

```
/usr/lib/nagios/plugins 
/usr/lib64/nagios/plugins
```

### Installing

Copy check_snmp_printer into your plugin directory and give it executable writes:

```
sudo cp ./check_snmp_printer /usr/lib64/nagios/plugins/
chmod a+x /usr/lib64/nagios/plugins/check_snmp_printer
```

Copy printers.conf into plugins-contrib.d folder:

```
sudo cp ./printers.conf /usr/share/icinga2/include/plugins-contrib.d/
```
Append services-printers.conf to the end of your Icinga2 services.conf:

```
cat ./services-printers.conf >> /etc/icinga2/conf.d/services.conf
```

If using Graphite, copy graphite templates to Icinga2 Graphite template folder:

```
sudo cp ./printer-consumables.ini /usr/share/icingaweb2/modules/graphite/templates/
sudo cp ./printer-trays.ini /usr/share/icingaweb2/modules/graphite/templates/
sudo cp ./printer-pagecount.ini /usr/share/icingaweb2/modules/graphite/templates/
```

If using Grafana, import JSON Dashboard (Graphite or InfluxDB) file and add graph dashboard information into module making sure to name the Dashboard printer-metrics:

![](img/GrafanaDashboardImport.png)

![](img/GrafanaLoadJSON.png)

```
sudo cat printer-metrics-graphs.ini >> /etc/icingaweb2/modules/grafana/graphs.ini
```

Restart Icinga2:

```
sudo systemctl restart icinga2
```

## Acknowledgments

* Franky Van Liedekerke for porting Jason Leonard's initial BASH script to Perl.
* Jason Leonard for writing the initial code that this was ultimately based upon.
