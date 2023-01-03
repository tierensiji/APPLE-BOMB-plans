# APPLE-BOMB-plans
苹果炸弹制作计划——解除已越狱设备IOS的温控。（150℃火力全开不香吗，遇到危险还能变身炸弹）

方法：
① 越狱设备下载安装filza文件管理器。并打开。
② filza进入下面的目录。
IOS12：/System/library/Watchdog/ThermalMonitor.bundle/<设备Model>.bundle
打开里面的 info.plist 文件
iOS 13、iOS 14：/System/library/ThermalMonitor/<设备Model>.plist
③ 单击直接打开这个plist文件，进入文件内的/ROOT下。
④ 删除 thermalMitigationLimits 和 contextualClampParams 两大项。
⑤ 进入/Root/hotspots ，Item 0 开始往下所有的Item <数字>，将以下项目（如果存在就改，不存在不用新建）数值修改成你需要的温度墙数值：（比如我要150℃温度墙就全部改150）
        ForcedThermalLevelTarget0

        ForcedThermalLevelTarget1

        ForcedThermalPressureLevelLightTarget

        THERMAL_TRAP_LOAD

        THERMAL_TRAP_SLEEP

        target
⑥ 修改完毕后保存退出，重启手机再越狱生效。
⑦ 如果开机后发现电池健康无法使用，或者提示手机电池为“维修”，则去cydia越狱商店下载安装一个battery电池健康修复的插件即可恢复正常。

备注：以上方案参考了https://www.bilibili.com/read/cv5036863，并由本人亲自实践优化完善而来。真实测试无论是geenkbench的CPU部分还是3d mark的GPU部分都显著超过没修改温度墙之前的水平，甚至超过了平均的同机型水平。
