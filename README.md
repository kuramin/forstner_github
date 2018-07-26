<html>
<body>
	<h2>Application of the Forstner keypoint detector</h2>
	<p>Laser scanning is a widely used survey technique which can be used for deformation analysis or 3D model creation. However, if scene is scanned from several points of view, the problem of point cloud correspondence arises. Registration of point clouds is an automatic procedure of data alignment, it finds matches between those parts of point clouds which are representations of the same objects. There
	are several known methods of registration such as ICP and 4PCS. Current project suggests a new one: an algorithm of registration based on radiometric features.</p>
	<p>Basic idea of current method is generation of an image from every point cloud, calculation of specific members by keypoint detector and definition of correspondences based on keypoint descriptors. The image created from a pointcloud which is a result of exterior scanning of Technicak University of Berlin and the result of Forstner keypoint detector application are the following:</p>
	<img src="Result_rect_gray_str.PNG" width = "500">
	<img src="Result_image_with_kpts_gray.PNG" width = "500"> <br> <br>
	<p>Further development of keypoint detection can be done in the direction of utilization of calibration matrix for the goal of creation of an undistorted image, so that keypoints could be defined more precisely. The following pair of images is the distorted full-color image of TU Berlin exterior wall and the result of usage of calibration matrix:</p>
	<img src="Result_rect_RGB.PNG" width = "500">
	<img src="Result_proj_RGB.PNG" width = "500"> <br> <br>
	Then detection of keypoints is performed on two scans of the same object. The following image shows keypoints of images and found matches:
	<img src="forstner_rooms.PNG">
	<p>After the definition of matching points the corresponding keypoints were found in the 3D point clouds. Thus, parameters of transformation between two point clouds were calculated. Application of these parameters as initial registration for ICP algorithm gives the following accurate result:</p>
	<img src="forstner_registration_precise.PNG">	
	<p>Algorithm itself, it's application and results are presented in a scientific article which was written by me and can be downloaded as a pdf-file: </p> 
	<p><a href="https://gitlab.tubit.tu-berlin.de/kuramin/forstner_keypoints_detector/tree/master/images/Ransac.pdf">Algorithm of intensity based registration for terrestrial laser scans.pdf</a> </p>
	<p>Code in C++ can be found on <a href="https://gitlab.tubit.tu-berlin.de/users/kuramin/projects">my Gitlab repository</a>.Execution of this project on the computer requires presence of OpenCV library.</p>
</body>
</html>