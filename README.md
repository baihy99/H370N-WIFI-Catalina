# H370N-WIFI-Catalina
## 系统版本：10.15.6

## 配置：  
机型：Macmin8,1  
主板：技嘉H370N WIFI  
CUP: i5 8400  
硬盘：三星 EVO 860 250GB SSD/希捷机械硬盘 2T  
独显：无  
  
## 引导程序：  
OpenCore 0.61  

## Bios设置： 
### Bios  
Bootup Numlock State: Off
Fast Boot : Disabled  
Windows8/10 Features: Windows8/10  
CSM Support: Disable  
Secure Boot Mode - Secure Boot Enable： disable  
Secure Boot Mode: Custom  
  
### Peripherals  
Initial Display Output : IGFX  
Intel Platform Trust Technology: Disable  
Software Guard Extensions Configurations: Disable  
Trusted Computing - Security Device Support: Disable  
Intel Bios Guard : Disable  
USB Configuration -  
Legacy USB Support: Enable  
XHCI Handoff：Enabled  
  
### Chipset  
VT-d：disable  
Integrated Graphics : Enabled  
Above 4G Decodeing: Enable  
  
## 解除CFG LOCK锁定：  
```
setup_var 0x5c1 0x0
```
操作方法：https://blog.csdn.net/shuiyunxc/article/details/104295837  
  
## 获取UUID  
WIN+R CMD  
输入：wmic  
再输入：csproduct  
得到如下UUID信息：  
    
 Caption|Description|IdentifyingNumber|SKUNumber|UUID|Vendor|Version
:--:|:--:|:--:|:--:|:--:|:--:|:--:
计算机系统产品|计算机系统产品|Default string|H370 WIFI|81AC7607-1E47-CB11-BC6A-8C7EF84170A7|Gigabyte Technology Co., Ltd.|Default string 
  
将得到的UUID填入OC config.plist 的 PlatformInfo - Generic - SystemUUID  
并修改MLB、SystemSerialNumber  
