---
Description: Method to perform a pre-check to determine whether a virtual system is likely to be successfully migrated to a target host specified by a network name or IP address.
ms.assetid: bfcd4063-30fe-4d18-9df9-7b84a680814c
title: CheckVirtualSystemIsMigratableToHost method of the CIM_VirtualSystemMigrationService class
ms.topic: reference
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- CIM_VirtualSystemMigrationService.CheckVirtualSystemIsMigratableToHost
api_type: 
- COM
api_location: 
- vmms.exe
---

# CheckVirtualSystemIsMigratableToHost method of the CIM\_VirtualSystemMigrationService class

Method to perform a pre-check to determine whether a virtual system is likely to be successfully migrated to a target host specified by a network name or IP address. This method does not guarantee that a subsequent migration will always succeed, due to dynamic resource availability.

Return code description:

Note: This method is intended as a transitional solution only until modeling of cluster support is available.

## Syntax


```mof
uint32 CheckVirtualSystemIsMigratableToHost(
  [in]  CIM_ComputerSystem REF ComputerSystem,
  [in]  string                 DestinationHost,
  [in]  string                 MigrationSettingData,
  [in]  string                 NewSystemSettingData,
  [in]  string                 NewResourceSettingData[],
  [out] boolean                IsMigratable
);
```



## Parameters

<dl> <dt>

*ComputerSystem* \[in\]
</dt> <dd>

A [**CIM\_ComputerSystem**](cim-computersystem.md) reference to the source virtual computer system to be migrated.

</dd> <dt>

*DestinationHost* \[in\]
</dt> <dd>

Target host system for the migration.

Acceptable formats for this parameter are conveyed through values of elements of the **DestinationHostFormatsSupported**\[ \] array property in the instance of the [**CIM\_VirtualSystemMigrationCapabilities**](cim-virtualsystemmigrationcapabilities.md) that is associated through the [**CIM\_ElementCapabilities**](cim-elementcapabilities.md) association.

</dd> <dt>

*MigrationSettingData* \[in\]
</dt> <dd>

String containing an embedded instance of the [**CIM\_VirtualSystemMigrationSettingData**](cim-virtualsystemmigrationsettingdata.md) class representing migration settings applicable to the migration operation.

</dd> <dt>

*NewSystemSettingData* \[in\]
</dt> <dd>

String containing an embedded instance of the [**CIM\_VirtualSystemSettingData**](cim-virtualsystemsettingdata.md) class representing new properties applicable to the virtual system after it is migrated.

</dd> <dt>

*NewResourceSettingData* \[in\]
</dt> <dd>

Array of strings each containing an embedded instance of the [**CIM\_ResourceAllocationSettingData**](cim-resourceallocationsettingdata.md) class representing new properties applicable to virtual resources in the scope of the virtual system after it is migrated.

</dd> <dt>

*IsMigratable* \[out\]
</dt> <dd>

The migration check result indicating whether or not the virtual system can be successfully migrated.

</dd> </dl>

## Return value

Returns a 0 on success; otherwise, returns an error.



| Return code/value                                                                                                                                                | Description                                                                                                                                                                                                                                                                                                                                                                            |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <dl> <dt>**Completed with No Error**</dt> <dt>0</dt> </dl>    | Check performed; result reported through the value of the \[Out\] *IsMigratable* parameter.<br/>                                                                                                                                                                                                                                                                                 |
| <dl> <dt>**Not Supported**</dt> <dt>1</dt> </dl>              | Method not supported by implementation. No result reported through the value of the \[Out\] *IsMigratable* parameter.<br/>                                                                                                                                                                                                                                                       |
| <dl> <dt>**Failed**</dt> <dt>2</dt> </dl>                     | Check failed for unspecified reasons. No result reported through the value of the \[Out\] *IsMigratable* parameter.<br/>                                                                                                                                                                                                                                                         |
| <dl> <dt>**Timeout**</dt> <dt>3</dt> </dl>                    | Check timed out. No result reported through the value of the \[Out\] *IsMigratable* parameter.<br/>                                                                                                                                                                                                                                                                              |
| <dl> <dt>**Invalid Parameter**</dt> <dt>4</dt> </dl>          | One or more parameters are formally invalid. For example, the value of the *DestinationHost* parameter could have been specified in an unsupported format. No result reported through the value of the \[Out\] *IsMigratable* parameter.<br/>                                                                                                                                    |
| <dl> <dt>**Invalid State**</dt> <dt>5</dt> </dl>              | The source virtual system, the source host system or the target host system are in a state that does allow initiation of the requested virtual system migration; this may be a temporary condition. No result reported through the value of the \[Out\] *IsMigratable* parameter.<br/>                                                                                           |
| <dl> <dt>**Incompatible Parameters**</dt> <dt>6</dt> </dl>    | One or more input parameters are incompatible as a set, or with respect to the target host. For example the value of the *MigrationNewSettingData* parameter contains properties that are not supported by the target host system identified by the value of the *DestinationHost* parameter. No result reported through the value of the \[Out\] *IsMigratable* parameter.<br/> |
| <dl> <dt>**DMTF Reserved**</dt> <dt>..</dt> </dl>             |                                                                                                                                                                                                                                                                                                                                                                                        |
| <dl> <dt>**Method Reserved**</dt> <dt>4097..32767</dt> </dl>  |                                                                                                                                                                                                                                                                                                                                                                                        |
| <dl> <dt>**Vendor Specific**</dt> <dt>32768..65535</dt> </dl> |                                                                                                                                                                                                                                                                                                                                                                                        |



 

## Requirements



| Requirement | Value |
|-------------------------------------|---------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 8.1<br/>                                                                                  |
| Minimum supported server<br/> | Windows Server 2012 R2<br/>                                                                       |
| Namespace<br/>                | Root\\virtualization\\v2<br/>                                                                     |
| MOF<br/>                      | <dl> <dt>WindowsVirtualization.V2.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>Vmms.exe</dt> </dl>                     |



## See also

<dl> <dt>

[**CIM\_VirtualSystemMigrationService**](cim-virtualsystemmigrationservice.md)
</dt> </dl>

 

 




