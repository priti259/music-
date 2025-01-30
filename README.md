# music- 1️⃣ Extract the ZIP File
If you haven't extracted it yet, run:

bash
Copy
Edit
unzip /mnt/data/multi_audio.zip -d ~/multi_audio_ws
Move into the workspace:

bash
Copy
Edit
cd ~/multi_audio_ws
2️⃣ Source ROS2 Environment
Ensure ROS2 Humble is installed and sourced:

bash
Copy
Edit
source /opt/ros/humble/setup.bash
3️⃣ Create a ROS2 Workspace (if needed)
If your project isn't inside a proper ROS2 workspace, create one:

bash
Copy
Edit
mkdir -p ~/multi_audio_ws/src
cd ~/multi_audio_ws
colcon build
Source the workspace:

bash
Copy
Edit
source install/setup.bash
4️⃣ Move Your Project to src (if required)
If your extracted files aren't inside src, move them:

bash
Copy
Edit
mv ~/multi_audio/* ~/multi_audio_ws/src/
5️⃣ Build the Workspace
bash
Copy
Edit
cd ~/multi_audio_ws
colcon build --symlink-install
If you see errors, install missing dependencies:

bash
Copy
Edit
rosdep install --from-paths src --ignore-src -r -y
Then rebuild:

bash
Copy
Edit
colcon build
6️⃣ Source the Workspace Again
bash
Copy
Edit
source install/setup.bash
To make it permanent:

bash
Copy
Edit
echo "source ~/multi_audio_ws/install/setup.bash" >> ~/.bashrc
source ~/.bashrc
7️⃣ Verify the Package
Check if the package is detected:

bash
Copy
Edit
ros2 pkg list | grep multi_audio
Run:

bash
Copy
Edit      
ros2 launch multi_audio your_launch_file.launch.py
(Replace your_launch_file.launch.py with your actual launch file.)
