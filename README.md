# Azure Database for PostgreSQL and MySQL - Single Server discovery

These Kusto queries show detailed lists of Single Servers on Azure.

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