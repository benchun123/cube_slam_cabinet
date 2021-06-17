# CubeSLAM in TUM Cabinet dataset, fork from [CubeSLAM](https://github.com/shichaoy/cube_slam). 

## directory
in folder /detect_3d_cuboid is a cmake file to deal with every frame  
in folder /ros_test is a ROS file to run online or offline SLAM  
every folder has its own data, and Thirdparty and should build independently. 

## how to run the project
1) to build essential thirdparty library  
cd detect_3d_cuboid/Thirdpary  
cd line_lbd  
mkdir build  
cd build  
cmake ..  
make  
>> it will output a library "libline_lbd_lib.so" in line_lbd/lib

cd detect_3d_cuboid/Thirdpary  
cd ticioc_profiler  
mkdir build  
cd build  
cmake ..  
make  
>> it will output a library "libtictoc_profiler.so" in ticioc_profiler/lib

cd ros_test/src/cube_slam/Thirdpary  
cd g2o  
mkdir build  
cd build  
cmake ..  
make  
>> it will output a library "libg2o.so" in g2o/lib

2) to build and run cmake code:    
cd detect_3d_cuboid  
mkdir build  
cd build  
cmake ..  
make  
./bbox_cabinet_det_node ../data #path_to_cabinet data
>> it can output "online_camera.txt" and "online_cube.txt" to save the result. 


3) to build and run visulazation code:  
cd ros_test/src  
catkin_init_workspace  
cd ..  
catkin_make
source devel/setup.bash    
roslaunch object_slam object_slam_example.launch   

