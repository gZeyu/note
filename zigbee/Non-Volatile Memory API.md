
# 10. Non-Volatile Memory API
## 10.1 Introduction
本节介绍 **OSAL** 非易失性( **NV** )内存系统。 该系统为应用程序提供了一种持久存储信息到设备内存中的方法。 堆栈还使用它来持久存储 **ZigBee** 规范所需的某些项目。 **NV**函数用于读取和写入由任意数据类型（如结构或数组）组成的用户定义项。 用户可以通过设置适当的偏移和长度来读取或写入整个项目或项目的元素。 **API** 独立于 **NV** 存储介质，可以用于 **flash** 或 **EEPROM** 。

每个 **NV** 项都有一个唯一的 **ID**。 应用程序有特定的 **ID** 值范围，而堆栈或平台保留或使用了某些 **ID** 值。 如果您的应用程序创建自己的 **NV** 项，则必须从“应用程序”值范围中选择一个 **ID** 。 见下表。
| VALUE | USER |
|--|--|
|VALUE |USER|
|0x0000 |Reserved|
|0x0001 – 0x0020 |OSAL|
|0x0021 – 0x0040 |NWK|
|0x0041 – 0x0060 |APS|
|0x0061 – 0x0080 |Security|
|0x0081 – 0x00B0 |ZDO|
|0x00B1 – 0x00E0 |Commissioning SAS|
|0x00E1 – 0x0100 |Reserved|
|0x0101 – 0x01FF |Trust Center Link Keys|
|0x0201 – 0x0300 |ZigBee-Pro: APS Links Keys <br>ZigBee-RF4CE: network layer|
|0x0301 – 0x0400 |ZigBee-Pro: Master Keys <br>ZigBee-RF4CE: app framework|
|0x0401 – 0x0FFF |Application|
|0x1000 - 0xFFFF |Reserved|
使用此API时有一些重要注意事项：
1. 这些是阻塞函数调用，操作可能需要几毫秒才能完成。 对于 **NV** 写入操作尤其如此。 此外，中断可能会被禁用几毫秒。 最好在它们与其他时序关键操作不冲突时执行这些功能。 例如，写入 **NV** 项的好时机就是接收器关闭时。
2. 尝试不经常执行 **NV** 写入。 这需要时间和力量; 大多数闪存设备也具有有限数量的擦除周期。
3. 如果一个或多个 **NV** 项的结构发生变化，尤其是从一个版本的TI堆栈软件升级到另一个版本时，则必须擦除并重新初始化 **NV** 存储器。 否则，对更改的 **NV** 项的读写操作将失败或产生错误结果。
## 10.2 `osal_nv_item_init()`
### 10.2.1 Description
初始化 **NV** 中的项目。 此功能检查 **NV** 中是否存在项目。 如果它不存在，则使用传递给函数的数据（如果有）创建并初始化它。
必须在为每个项调用`osal_nv_read()`或`osal_nv_write()`之前，调用此函数。
### 10.2.2 Prototype
``` c
uint8 osal_nv_item_init( uint16 id, uint16 len, void *buf );
```
### 10.2.3 Parameter Details
`id` – 用户定义项ID。
`len` – 项长度，以字节为单位。
`*buf` – 指向项初始化数据的指针。 如果没有初始化数据，则设置为NULL。
### 10.2.4 Return
返回值表示操作的结果。
## 10.3 osal_nv_read( )
### 10.3.1 Description
从 **NV** 读取数据。 此功能可用于从 **NV** 中读取整个项或者通过偏移量来读取 **NV** 项的元素。被读取的数据被复制到`* buf`中。
### 10.3.2 Prototype
``` c
uint8 osal_nv_read( uint16 id, uint16 offset, uint16 len, void *buf );
```
### 10.3.3 Parameter Details
`id` – 用户定义项 **ID**。
`offset` – 在 **NV** 项中的偏移量，以字节为单位。
`len` – 项长度，以字节为单位。
`*buf` – 指向被读取的数据的指针。
<!--stackedit_data:
eyJoaXN0b3J5IjpbNzU1MDY2MzYsLTE2ODQ0MDMzMTMsMTE3Mj
MzMDk2NiwtMTI2NTc5MDM5MiwyMDg0NzQ4MTEyLDEwOTM1NjAx
MTAsMTYxMjM5MTE4MSwxNjgzNDUzNzA1LDE1NTY5NjIzN119
-->