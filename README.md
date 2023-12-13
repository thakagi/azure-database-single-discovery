# Discovering Azure Database for PostgreSQL and MySQL - Single Server

The following Kusto query will help you find existing Single Servers in Azure Resource Graph. Please note that you need read access to the resources you are querying to obtain the results.

## Azure Database for PostgreSQL - Single Server

```SQL
resources
| where type == "microsoft.dbforpostgresql/servers"
| project
    name,
    type,
    subscriptionId,
    sku = sku["name"],
    tier = sku["tier"],
    capacity = sku["capacity"],
    family = sku["family"],
    location,
    version = properties["version"],
    publicNetworkAccess = properties["publicNetworkAccess"],
    privateEndpointConnections = properties["privateEndpointConnections"],
    backupRetentionDays = properties["storageProfile"]["backupRetentionDays"],
    geoRedundantBackup = properties["storageProfile"]["geoRedundantBackup"],
    storageAutogrow = properties["storageProfile"]["storageAutogrow"],
    storageMB = properties["storageProfile"]["storageMB"],
    fullyQualifiedDomainName = properties["fullyQualifiedDomainName"],
    minimalTlsVersion = properties["minimalTlsVersion"],
    replicationRole = properties["replicationRole"],
    replicaCapacity = properties["replicaCapacity"],
    infrastructureEncryption = properties["infrastructureEncryption"],
    userVisibleState = properties["userVisibleState"],
    byokEnforcement = properties["byokEnforcement"],
    sslEnforcement = properties["sslEnforcement"],
    tags
```

## Azure Database for MySQL - Single Server

```SQL
resources
| where type == "microsoft.dbformysql/servers"
| project
    name,
    type,
    subscriptionId,
    sku = sku["name"],
    tier = sku["tier"],
    capacity = sku["capacity"],
    family = sku["family"],
    location,
    version = properties["version"],
    publicNetworkAccess = properties["publicNetworkAccess"],
    privateEndpointConnections = properties["privateEndpointConnections"],
    backupRetentionDays = properties["storageProfile"]["backupRetentionDays"],
    geoRedundantBackup = properties["storageProfile"]["geoRedundantBackup"],
    storageAutogrow = properties["storageProfile"]["storageAutogrow"],
    storageMB = properties["storageProfile"]["storageMB"],
    fullyQualifiedDomainName = properties["fullyQualifiedDomainName"],
    minimalTlsVersion = properties["minimalTlsVersion"],
    replicationRole = properties["replicationRole"],
    replicaCapacity = properties["replicaCapacity"],
    infrastructureEncryption = properties["infrastructureEncryption"],
    userVisibleState = properties["userVisibleState"],
    byokEnforcement = properties["byokEnforcement"],
    sslEnforcement = properties["sslEnforcement"],
    tags
```