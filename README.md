# Object_localisation_with_pointclouds
Determining the pose of an object from pointclouds using U-Net


A point cloud from Azurekinect is subscribed and processed to find the pose of the interested objects in the pointclouds. The detection of objects is done using U-Net. Later, a postprocessing method follows it. This is because U-Net is only a segmentation model. Therefore, a postprocess is introduced to divide the segmented output to instances of objects using classical image proprocessing methods. Then, from the detected objects using pointclouds, the pose of the objects are detected. These poses are then used to pick and place the objects according to the requirements.


Dependencies needed:
1. ROS
2. Azure kinect ROS setup
3. ROS Melodic with python3
4. Tensorflow >2.3.0
5. numpy
6. ros_pcl
7. open3d
8. opencv


Process flow:
1. Load the trained model.
2. Subscribe to the points2 topic from the Azurekinect.
3. Separate the rgb image from point cloud.
4. Predict the image using model.
5. Do the postprocessing to get instances.
6. Determine the pose of the objects from instances.
7. Feed the poses in for-loop to perform pick and place action via xmlrpc communication with the robot.



Disclaimer:  This is a work in progress. Therefore, it needs to be optimised and documented properly.
