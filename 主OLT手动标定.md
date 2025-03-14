


clear optic para flag device 1
load optic par by tftp device 1 svrip 192.168.100.1 par_name optic_init_par_HS0701.bin


bosa reset device 1
# 仪器波长设置为1490nm
set bosa table 0xA2 addr 0x7F len 1 value 0x80
# 调整光功率，光功率目标值为3±0.3dBm
set bosa table 0xA2 addr 0x83 len 1 value 0x10

## 二、发端标定---光功率&消光比标定

# 调整MOD阈值到最大
# 调整APC，8D表示光功率，8E[7:2]默认，8E[1:0]表示APC最后两位
set bosa table 0xA2 addr 0x8D len 2 value 0x1320
get bosa table 0xA2 addr 0x8D len 2
# 调整消光比，88表示MOD电流高8位
set bosa table 0xA2 addr 0x88 len 1 value 0x79
get bosa table 0xA2 addr 0x88 len 1

# 参数写入
# apc目标值写入
set bosa table 0x299F addr 0x4A6 len 2 value 0x1420
get bosa table 0x299F addr 0x4A6 len 2
# mod目标值
set bosa table 0x299F addr 0x4A1 len 2 value 0x83e0
get bosa table 0x299F addr 0x4A1 len 2

## 三、收端端标定---RXSD标定

# 从网关输入光-23dBm
set bosa table 0xA2 addr 0x7F len 1 value 0x80
# RX_SD门限
set bosa table 0xA2 addr 0xAD len 1 value 0x31
get bosa table 0xA2 addr 0xAD len 1

# 输入光功率-23dBm，将RXSD阈值从大值向下调整，直到触发SD，返回1为止
# 如果调试档位过大，触发后再次调整RXSD阈值需将光纤拔掉后再测试是否触发，以免落入回滞区间
get optic los status

# RXSD写入
set bosa table 0x299F addr 0x125 len 1 value 0x14
get bosa table 0x299F addr 0x125 len 1

# 刷新CRC
chipdebug print on
save optic para
set bosa table 0x299F addr 0x08 len 4 value 0xca711ec2
save optic para
bosareset
chipdebug print off


