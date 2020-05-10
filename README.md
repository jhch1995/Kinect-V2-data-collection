# KinectV2_dataset
通过catkin_make对源文件进行编译
编译生成的可执行程序应该在: catkin_make/devel/lib/dataset_make/get_image_node

# 执行操作
1. 发布kinetic的相关的话题：
roslaunch kinect2_bridge kinect2_bridge.launch
2. 启动可执行程序
./get_image_node
3. 生成associate.txt
python associate.py rgb.txt depth.txt >associations.txt
对应的txt文件可以通过上面的步骤得到
-----
注意：
1. 需要在get_image.cpp文件中的save_path中给出图片的存储的路径(给定的是最上级文件夹，会自动生成depth,rgb文件夹以及对应的txt文件)
2. 订阅的话题可能需要修改:  rostopic list  
   看是否为/kinect2/qhd/image_color和/kinect2/qhd/image_depth_rect
3. 需要将存储的图片数进行调整，源文件给出的为500，实际的数据集大小一般为2400-2700张
4. 需要提前在制定文件夹下新建rgb和depth的文件夹
