# 基於ROS的機器人地圖探索系統
本專題目標在實現一款基於ROS的自主地圖探索機器人，並在Gazebo模擬環境中驗證其功能。該機器人支持自動構建環境地圖、將生成的地圖存檔以及重新加載已保存地圖等操作。
## 倉庫目錄說明如下：
1. **robot**：
   **URDF文件**：用於定義機器人的結構、連桿關節和感測器佈局。
   **.world文件**：提供帶障礙物和地形的模擬環境，供機器人運動測試。
2. **m-explore**：
   基於開源的 explore_lite 探索演算法，用於在未知空間中尋找邊界並逐步擴展地圖，確保機器人能全面覆蓋環境並動態適應不同場景。
3. **auto_nav**：
   負責自動建圖與導航的 ROS 組合包。
4. **scripts**
   存放各類輔助腳本，當中 next_goal.py 會動態計算並發佈下一個移動目標點，保證機器人能連續、高效地覆蓋所有待掃區域。
## 如何操作
1. **掃描建圖**：
   指令：`roslaunch auto_nav auto_slam.launch` 
2. **儲存地圖**
   開啟另一個終端機
   指令：`roslaunch auto_nav save_map.launch` 
3. **開啟儲存好的地圖**
   關閉第一個指令再操作
   指令：`roslaunch auto_nav amcl.launch`
## 如何下載
```bash
   cd ~/catkin_ws/src
   git clone https://github.com/zy0913zy/Explore_robot.git
   cd ..
   catkin_make
```
## 影片
   https://youtu.be/CseWEquCzXg
## 系統設計
![auto_slam_rosgraph](https://github.com/user-attachments/assets/a7c012fa-0150-4a8b-9d07-dae79de37fc8)





