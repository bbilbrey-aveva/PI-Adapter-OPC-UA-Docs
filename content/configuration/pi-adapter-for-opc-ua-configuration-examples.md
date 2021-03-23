---
uid: PIAdapterForOPCUAConfigurationExamples
---

# PI Adapter for OPC UA configuration examples

The following tables provide examples for all configurations available for PI Adapter for OPC UA.

**Note:** The examples in this topic are using the default port number `5590`. If you selected a different port number, replace it with that value.

## System components configuration with two OPC UA adapter instances

```json
[
    {
        "ComponentId": "OpcUa1",
        "ComponentType": "OpcUa"
    },
    {
        "ComponentId": "OpcUa2",
        "ComponentType": "OpcUa"
    },
    {
        "ComponentId": "OmfEgress",
        "ComponentType": "OmfEgress"
    }
]
```

## OPC UA adapter configuration

```json
{
    "OpcUa1": {
        "Logging": {
            "logLevel": "Information",
            "logFileSizeLimitBytes": 34636833,
            "logFileCountLimit": 31
        },
        "DataSource": {
            "EndpointUrl": "opc.tcp://OPCUAServerEndpoint/OPCUA/Server",
            "UseSecureConnection": false,
            "StreamPrefix": "OPC_Prefix_",
            "UserName": null,
            "Password": null,
            "RootNodeIds": null,
            "IncomingTimestamp": "Source",
            "applyPrefixToStreamId": true
        },
        "DataSelection": [
            {
                "Selected": true,
                "Name": "Sawtooth",
                "NodeId": "ns=3;s=Sawtooth",
                "StreamId": "SawtoothStream"
            }
        ]
    },
    "System": {
        "Logging": {
            "logLevel": "Information",
            "logFileSizeLimitBytes": 34636833,
            "logFileCountLimit": 31
        },
        "HealthEndpoints": [
        ],
    "Diagnostics": {
            "enableDiagnostics": true
    },
        "Components": [
            {
                "componentId": "Egress",
                "componentType": "OmfEgress"
            },
            {
                "componentId": "OpcUa1",
                "componentType": "OpcUa"
            }
        ],
    "Buffering": {
            "BufferLocation": "C:/ProgramData/OSIsoft/Adapters/OpcUa/Buffers",
            "MaxBufferSizeMB": -1,
            "EnableBuffering": true
        }
     },
    "OmfEgress": {
        "Logging": {
            "logLevel": "Information",
            "logFileSizeLimitBytes": 34636833,
            "logFileCountLimit": 31
        },
        "DataEndpoints": [
            {
                "id": "WebAPI EndPoint",
                "endpoint": "https://PIWEBAPIServer/piwebapi/omf",
                "userName": "USERNAME",
                "password": "PASSWORD"
            },
            {
                "id": "OCS Endpoint",
                "endpoint": "https://OCSEndpoint/omf",
                "clientId": "CLIENTID",
                "clientSecret": "CLIENTSECRET"
            },
            {
                "Id": "EDS",
                "Endpoint": "http://localhost:/api/v1/tenants/default/namespaces/default/omf",
                "UserName": "eds",
                "Password": "eds"
            }
        ]
    }
}
```

## Data source configuration

The following are representations of minimal and complete data source configurations of OPC UA adapter.

### Minimal data source configuration

```json
{
    "EndpointUrl": "opc.tcp://<IP-Address>:<Port>/<TestOPCUAServer>"
}
```

### Complete data source configuration

```json
{
    "EndpointUrl": "opc.tcp://<IP-Address>:<Port>/<TestOPCUAServer>",
    "UseSecureConnection": true,
    "UserName": null,
    "Password": null,
    "RootNodeIds": null,
    "IncomingTimestamp": "Source",
    "StreamIdPrefix": null,
    "DefaultStreamIdPattern": "{NamespaceIndex}.{Identifier}"
}
```

## Client settings configuration

```json
{
    "maxBrowseReferencesToReturn": 0,
    "BrowseBlockSize": 10,
    "ReadBlockSize": 1000,
    "reconnectDelay": "0:00:30",
    "recreateSubscriptionDelay": "0:00:05",
    "sessionRequestTimeout": "0:02:00",
    "connectionTimeout": "0:00:30",
    "sessionAllowInsecureCredentials": false,
    "sessionMaxOperationsPerRequest": 1000,
    "browseTimeout": "0:01:00",
    "ReadTimeout": "0:00:30",
    "maxMonitoredItemsPerCall": 1000,
    "maxNotificationsPerPublish": 0,
    "publishingInterval": "0:00:01",
    "createMonitoredItemsTimeout": "0:00:30",
    "samplingInterval": "0:00:00.5",
    "monitoredItemQueueSize": 2,
    "maxInternalQueueSize": 500000
}
```

## Data selection configuration

The following are representations of minimal and complete data selection configurations of OPC UA adapter.

### Minimal data selection configuration

```json
[
 {
    "NodeId": "ns=5;s=Random1"
  },
  {
    "NodeId": "ns=5;s=Sawtooth1"
  },
  {
    "NodeId": "ns=5;s=Sinusoid1"
  }
]
```

### Complete data selection configuration

```json
[
 {
    "Selected": true,
    "Name": "CustomStreamName",
    "NodeId": "ns=5;s=Random1",
    "StreamId": "CustomStreamName"
  },
  {
    "Selected": false,
    "Name": null,
    "NodeId": "ns=5;s=Sawtooth1",
    "StreamId": null
  },
  {
    "Selected": true,
    "Name": "5.Sinusoid1",
    "NodeId": "ns=5;s=Sinusoid1",
    "StreamId": null
  }
]
```
