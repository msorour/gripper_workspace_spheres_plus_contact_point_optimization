Dependency:
Please install [quadprog++](https://github.com/liuq/QuadProgpp)

To run this algorithm:
1. make sure to remove the build folder and make a new one (this is done only once):
rm -r build/ && mkdir build

2. use the following command in the build folder:
reset && cmake .. && make -j7 && ./grasping_algorithm ../gripper_pcd_model/allegro_right_hand_model_cloud_plus_camera_downsampled_100.pcd 3_view ../3_view_object_pcd_files/cup_without_handle 4 4 4 3 3 3
reset && cmake .. && make -j7 && ./grasping_algorithm ../gripper_pcd_model/allegro_right_hand_model_cloud_plus_camera_downsampled_100.pcd single ../single_view_object_pcd_files/cocacola_bottle.pcd 10 10 10 7 7 7

The algorithm takes 9 input arguments:
1. the gripper point cloud (currently you can use the the allegro hand "allegro_right_hand_model_cloud_plus_camera_downsampled_100.pcd" and the Franka panda gripper "franka_gripper_model_cloud_plus_camera_downsampled_100.pcd")
2. object point coud type ( "3_view" point cloud along with their respective transformation matrices or a "single" view point cloud (complete one generated by CAD model or which ever source))
3. 3 view object point cloud base name (the algorithm will search for 4 files with this base name, 3 for the 3 view point cloud and one .txt containing thier transformation matrices in robot arm base frame) or the single view point cloud file
4. number of orientation samples about x, y, and z axes (3 inputs)
5. number of position samples in x, y, and z axes (3 inputs)

The output is a transformation matrix to be applied to the end effector frame of the robot arm to realize the gripper 6D pose generated by the algorithm.

TODO:
1. allow supplying the transformation matrix of the camera frame with respect to end-effector frame as input.
2. allow supplying the transformation matrix of the gripper frame with respect to end-effector frame as input.

More details on the algorithm can be found in this [IROS 2019 paper](http://eprints.lincoln.ac.uk/36370/1/IROS19_1656_MS.pdf):

Have fun!
