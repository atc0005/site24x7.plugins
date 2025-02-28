# Aerospike Namespace Monitoring

                                                                                            
## Prerequisites

- Download and install the latest version of the [Site24x7 Linux agent](https://www.site24x7.com/app/client#/admin/inventory/add-monitor) in the server where you plan to run the plugin. 

- Install aerospike module for python
```
  pip3 install aerospike
```
---



### Plugin Installation  

- Create a directory named "aerospike_namespace_monitoring".
      
- Download all the files in the "aerospike_namespace_monitoring" folder and place it under the "aerospike_namespace_monitoring" directory.

		wget https://raw.githubusercontent.com/site24x7/plugins/master/aerospike_monitoring/aerospike_namespace_monitoring/aerospike_namespace_monitoring.py
		wget https://raw.githubusercontent.com/site24x7/plugins/master/aerospike_monitoring/aerospike_namespace_monitoring/aerospike_namespace_monitoring.cfg

- Execute the following command in your server to install aerospike: 

		pip3 install aerospike

- Execute the below command with appropriate arguments to check for the valid json output:

		python3 aerospike_namespace_monitoring.py --hostname=<name of the host> --port=<port> --tls_enable=<true/false> --tls_name=<tls name> --cafile=<cafile path>  --username=<username> --password=<password>  --node_id=<node id> --namespace=<namespace>


- Move the directory "aerospike_namespace_monitoring" under Site24x7 Linux Agent plugin directory.


---

### Configurations

- Provide your aerospike_namespace_monitoring configurations in aerospike_namespace_monitoring.cfg file.
```
    [Aerospike Namespace Monitoring]
    hostname=<HOSTNAME>
    port=<PORT>
    tls_enable=false
    tls_name=None
    cafile=None
    username=<USERNAME>
    password=<PASSWORD>
    node_id=<NODE ID>
    namespace=<NAMESPACE>
    logs_enabled=False
    log_type_name=<LOG TYPE NAME>
    log_file_path=<LOG FILE PATH>
```	

The agent will automatically execute the plugin within five minutes and send performance data to the Site24x7 data center.

## Supported Metrics
The following metrics are captured in the aerospike_namespace_monitoring Plugin

- **Dead Partitions**

    The number of dead partitions for this namespace 

- **Memory Free %**

     The percentage of disk capacity free for this namespace

- **Unavilable Partitions**

    The number of unavilable partitions for this namespace

- **Client Delete Error**

    The number of client delete transactions that failed with an error


- **Client Read Error**

    The number of client read transactions that failed with an error


- **Client UDF Error**

    The number of failed udf transactions initiated by the client.

- **Client Write Error**

    The number of failed write transactions initiated by the client.

- **Memory Used Bytes**

    Memory used in bytes


- **Pi Query Aggr Error**

    The number of aggregations fail due to an internal error seen by this node


- **Clock Skew Stop Writes**

    True if clock skew is outside of tolerance for strong-consistency


- **Stop Writes**

    True if this namespace is currently not allowing writes.
