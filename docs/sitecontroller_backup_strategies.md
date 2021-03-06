# SiteController Backup Strategies

## Central Site Controller

Currently the Central Site Controller is not the source of truth for any data.  It should be able to be regenerated from those other data sources.

### Bastion

* SSH Keys - These are stored in an encrypted keepass vault in GHE

### Mirror

* sitecontroller-envs has dicts of data which tells it how to collect the appropriate materials

### IPMI Proxy

* data for servers is polled from BoxPanel 

### Control Proxy 

* sitecontroller-envs has a dict of data which it uses to build out the control proxy.

## Remote Site Controller

### Bootstrapper

* contents of bootstrapper ( squid, pxe, etc ) is generated by sitecontroller-envs data

### ELK

* ELK configs are generated by sitecontroller-envs data
* ELK LOG Data is replicated across multiple servers.

### Monitoring Data

* sensu, graphite, etc settings are generated by sitecontroller-envs
* graphite data is not backed up as it is not considered critical
