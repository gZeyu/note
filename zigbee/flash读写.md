
0x0000 保留

0x0001~0x0020 操作系统抽象层（OSAL）

0x0021~0x0040 网络层（NWK）

0x0041~0x0060 应用程序支持子层（APS）

0x0061~0x0080 安全（Security）

0x0081~0x00A0 Zigbee设备对象（ZDO）

0x00A1~0x0200 保留

0x0201~0x0FFF 应用程序

0x1000~0xFFFF 保留

``` c
#define OSAL_NV_PAGE_SIZE       HAL_FLASH_PAGE_SIZE
#define OSAL_NV_PAGES_USED      HAL_NV_PAGE_CNT
#define OSAL_NV_PAGE_BEG        HAL_NV_PAGE_BEG
#define OSAL_NV_PAGE_END       (OSAL_NV_PAGE_BEG + OSAL_NV_PAGES_USED - 1)
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTkwNDY5NzkxNSwtMTI3ODk3NzU5OF19
-->