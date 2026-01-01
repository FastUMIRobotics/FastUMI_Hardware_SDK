# FastUMI Hardware sdk

## 📁 Directory Structure

```
vive/                                 # Vive tracking system resources
├── doc/                              # Vive usage and configuration documentation
│   ├── FastUMI_Hardware_Startup_Procedure_en.docx  # FastUMI hardware startup procedure (EN)
│   ├── FastUMI_Hardware_Startup_Procedure_zh.docx  # FastUMI hardware startup procedure (CN)
│   └── Vive_Usage_Guide_zh.docx                     # Vive basic usage guide

xv/                                   # FastUMI Core SDK (XV SDK & ROS Support)
├── doc/                              # FastUMI hardware, interfaces, and ROS documentation
│   ├── README-Interfaces.md          # Hardware interfaces and data specifications
│   ├── README-ros1.md                # ROS 1 usage guide
│   ├── README-ros2.md                # ROS 2 usage guide
│   ├── ros1-topic 介绍.docx          # ROS 1 topic reference
│   └── ros2-topic 介绍.docx          # ROS 2 topic reference
│
├── scripts/                          # SDK installation and system configuration scripts
│   ├── 99-xvisio.rules               # udev rules (device permission configuration)
│   ├── README-install.md             # SDK installation instructions
│   ├── install-ros1.sh               # One-click installation for SDK + ROS 1 packages
│   ├── install-ros2.sh               # One-click installation for SDK + ROS 2 packages
│   ├── install-python.sh             # Python runtime environment installation script
│   └── multi-support.sh              # USB bandwidth expansion (required for multi-device setups)
│
├── sdk/                              # FastUMI hardware SDK packages (versioned by release)
│   └── XXX/                          # SDK version directory (delivery-based)
│       ├── XVSDK_focal_amd64_XXX.deb  # Ubuntu 20.04 / ROS 1
│       └── XVSDK_jammy_amd64_XXX.deb  # Ubuntu 22.04 / ROS 2
 
```

### Document Description

| Files | Features | Use Cases |
|------|------|---------|

---

## 🚀 Quick Start

### Prerequisites

1. **ROS Environment Installation**
   ```bash
   #Recommend ROS1 neotic
   wget http://fishros.com/install -O fishros && . fishros
   ```
---

## 📖 Use Guides (Single/Double Device Universal)

1. **Installing the SDK**
   ```bash
   cd xv/scripts/
   #ros1 Version(recommended)
   sudo -E bash install-ros1.sh ../sdk/XXX/XVSDK_focal_amd64_XXX.deb
   ```
   
   ```bash
   cd xv/scripts/
   #ros2 Version
   sudo -E bash install-ros2.sh ../sdk/XXX/XVSDK_jammy_amd64_XXX.deb
   ```

2. **Connecting FastUMI**
   ```bash
   cd ~/catkin_ws/
   roslaunch xv_sdk xv_sdk.launch

   ```
   
3. **Extending USB bandwidth (optional, must be done first when multiple devices are used)**
   ```bash
   #The terminal automatically restarts after execution
   sudo -E bash multi-support.sh
   ```
   
3. **Checking FastUMI Status**
Sampling analysis of device collection data can be performed via [FastUMI Monitor Tool] (https://github.com/FastUMIRobotics/FastUMI_Monitor_Tool) to see if the device‘s operational status is normal.
---



## 🔍 Troubleshooting

### Problem: SDK roslaunch startup fails

**Check：**
Delete the related process and restart the SDK.


