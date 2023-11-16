# MSI-PRO-Z790-A-MAX-WIFI-D5-14700KF-RX6650XT-EFI
MSI PRO Z790-A MAX WI-FI D5 + 14700KF + RX6650XT EFI Hackintosh

# 硬件说明

- 主板：MSI PRO Z790-A MAX WIFI DDR5
- CPU：Intel i7 14700KF
- 内存：Gloway 64GB (32G x 2)
- 显卡：MSI Radeon RX6650XT MECH 2X 8G OC
- 硬盘：FANXIANG 2TB SSD M2 PCIe 4.0 x4
- WI-FI+蓝牙：FENVI T919 BCM943602CS PCIe x1

# 完成度

- 主板板载有线网卡驱动成功（Intel i225-V）
- CPU睿频成功，360水冷，日常温度38度
- 显卡驱动成功，目前双显示器输出，一个27的1080P，一个27的2K
- WIFI + 蓝牙免驱，隔空投送成功，连接蓝牙音箱成功
- 休眠唤醒成功

# Geekbench 6.2.1 跑分结果

- CPU单核：2861 / 优化后：3004 （提升5%）
- CPU多核：18007 / 优化后：20270 （提升12%）
- GPU显卡：119013（Metal）

# Sensei 1.5.7 硬盘基准测试

- 硬盘：读6.1GB/s，写5.9GB/s(硬盘标称读7.4GB/s)

# 使用说明

- 如果用的不是我的同款主板，请自己定制USB端口
- 如果不需要屏蔽NVME硬盘，请取消ACPI里SSDT-NVME-DISABLE，我这里是把装Windows 11的固态盘在MACOS里屏蔽掉了

# 优化记录

- 2023-10-30 增加`-ctrsmt`引导参数，提升CPU性能表现
- 2023-10-31 优化系统更新，解决小版本更新下载推送的问题
- 2023-11-09 支持OpenCore 0.9.6

# 双系统蓝牙连接问题解决方法
### 问题：在Windows 11里配对好蓝牙音箱（或鼠标、键盘），可以正常使用，回到Mac OS里配对同一蓝牙音箱，有部分设备就会连接不上，导致每次换个系统都需要重新配对

### 原因：由于每次配对时，不同系统生成的连接KEY不同，导致音箱（蓝牙设备）不能通过认证

### 解决方法

1. 在Windows里配对蓝牙设备，正常连接使用
2. 重新启动，进入macOS，重新配对蓝牙设备，可正常使用后，记录蓝牙设备MAC地址，关闭蓝牙设备电源（必须关闭电源，否则下一步无法导出此设备的连接Key）
3. 在macOS中下载安装 [hackintool](https://github.com/benbaker76/Hackintool)，启动hackintool，点击上部工具图标，再点击UI底部的蓝牙图标，生成Windows蓝牙注册表文件，保存后，将文件复制到U盘
4. 重启进入Windows系统，打开注册表编辑器，将刚才导出的蓝牙注册表文件导入，如果提示不能访问注册表，在注册编辑器中的HKEY_LOCAL_MACHINE单击右键，选择权限，继承勾选上，然后应用，再重新导入即可
5. 导入后重启Windows，打开蓝牙设备电源，此时可以直接连接蓝牙设备
6. 重启进入macOS，也可以直接连接蓝牙设备，至此问题解决