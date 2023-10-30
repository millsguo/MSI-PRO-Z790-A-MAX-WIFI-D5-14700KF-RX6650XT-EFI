# MSI-PRO-Z790-A-MAX-WIFI-D5-14700KF-RX6650XT-EFI
MSI PRO Z790-A MAX WIFI D5 + 14700KF + RX6650XT EFI Hackintosh

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
- 如果不需要屏蔽NVME硬盘，请取消ACPI里SSDT-NVME-DISABLE

# 优化记录

- 增加`-ctrsmt`引导参数，提升CPU性能表现