# Multi-Audio ROS2 Package

## 📌 Overview
The **multi_audio** package is a ROS2-based implementation for managing and publishing audio playback requests in a robotic system. It allows users to select and play different audio files using ROS2 topics.

---

## 📂 Project Structure
```
multi_audio_ws/
│── src/
│   ├── multi_audio/        # ROS2 Package Directory
│   ├── CMakeLists.txt      # Build system configuration
│   ├── package.xml         # ROS2 Package Metadata
│   ├── launch/             # ROS2 Launch Files
│   ├── scripts/            # Python Nodes
│   ├── config/             # Configuration Files
│   └── ...
│── install/                # Built workspace (after colcon build)
│── build/                  # Temporary build files
│── log/                    # Logs and debugging info
└── README.md               # This file
```

---

## 🚀 Installation & Setup
Follow these steps to set up the **multi_audio** package in your ROS2 workspace.

### **1️⃣ Extract the Project Files**
```bash
unzip multi_audio.zip -d ~/multi_audio_ws
cd ~/multi_audio_ws
```

### **2️⃣ Source ROS2 Environment**
Ensure ROS2 Humble is installed and sourced:
```bash
source /opt/ros/humble/setup.bash
```

### **3️⃣ Create a ROS2 Workspace (if not already created)**
```bash
mkdir -p ~/multi_audio_ws/src
cd ~/multi_audio_ws
colcon build
source install/setup.bash
```

### **4️⃣ Move the Package into `src/` (if required)**
```bash
mv ~/multi_audio/* ~/multi_audio_ws/src/
```

### **5️⃣ Install Dependencies & Build the Workspace**
```bash
cd ~/multi_audio_ws
rosdep install --from-paths src --ignore-src -r -y
colcon build --symlink-install
```

### **6️⃣ Source the Workspace (Permanent Setup)**
```bash
source install/setup.bash

# To automatically source in new terminals
echo "source ~/multi_audio_ws/install/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

### **7️⃣ Verify the Package**
Check if the package is correctly installed:
```bash
ros2 pkg list | grep multi_audio
```

### **8️⃣ Launch the Package**
```bash
ros2 launch multi_audio your_launch_file.launch.py
```
(Replace `your_launch_file.launch.py` with the actual launch file in your package.)

---

## 📌 Usage
- Run the **audio publisher node** to publish a song request.
- Ensure the **audio player node** is running and subscribed to the topic.
- Select a song from the provided list when prompted.

---

## 📌 Contribution
Feel free to contribute to this project by:
- Reporting issues
- Submitting feature requests
- Creating pull requests

---

## 📌 License
This project is licensed under the **Apache 2.0 License**. See the `LICENSE` file for details.

---

## 📌 Contact
For any queries, reach out via GitHub Issues or email.

Happy coding! 🚀

