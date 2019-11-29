To run this algorithm:
1. make sure to remove the build folder and make a new one (this is done only once):
rm -r build/ && mkdir build

2. use the following command in the build folder:
reset && cmake .. && make -j7 && ./grasping_algorithm ../gripper_pcd_model/allegro_right_hand_model_cloud_plus_camera_downsampled_100.pcd 3_view ../raw_object_pcd_files/cup_without_handle

The algorithm takes 3 input arguments:
1. the gripper point cloud
2. object point coud type (currently a 3 view point cloud along with their respective transformation matrices is only implemented)
3. 3 view object point cloud base name (the algorithm will search for 4 files with this base name, 3 for the 3 view point cloud and one .txt containing thier transformation matrices in robot arm base frame)

Have fun!
