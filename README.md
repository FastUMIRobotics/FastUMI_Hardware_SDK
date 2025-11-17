# FastUMI硬件sdk

## 📁 目录结构

```
doc/				  # 硬件相关资料
scripts/			  # sdk安装脚本
├── install-ros1.sh              # 一键安装sdk及ros1功能包
├── install-ros2.sh              # 一键安装sdk及ros2功能包
├── install-python.sh            # 一键安装sdk及python运行环境
├── multi-support.sh             # 扩展usb带宽，支持多设备运行环境
sdk/				  # 硬件安装包，按交付时间归档版本
├── XVSDK_focal_amd64_XXX.deb    # ROS1版本
├── XVSDK_jammy_amd64_XXX.deb    # ROS2版本
```

### 文件说明

| 文件 | 功能 | 使用场景 |
|------|------|---------|

---

## 🚀 快速开始

## 📖 使用指南（单/双设备通用）

1. **安装SDK**
   ```bash
   cd scripts
   #ros1版本(recommended)
   sudo -E bash install-ros1.sh ../sdk/XXX/XVSDK_focal_amd64_XXX.deb
   ```
   
   ```bash
   cd scripts
   #ros2版本
   sudo -E bash install-ros2.sh ../sdk/XXX/XVSDK_jammy_amd64_XXX.deb
   ```

2. **连接FastUMI**
   ```bash
   cd ~/catkin_ws/
   roslaunch xv_sdk xv_sdk_launch

   ```
   
3. **检查FastUMI状态**
可通过[FastUMI Monitor Tool](https://github.com/FastUMIRobotics/FastUMI_Monitor_Tool)对设备采集数据进行采样分析，查看设备运行状态是否正常。
---


## 🔍 故障排查

### 问题：SDK roslaunch启动失败

**检查：**
删除相关进程，重新启动SDK。


