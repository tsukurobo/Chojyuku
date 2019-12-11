# Chojyuku


パッケージ


#ｃｈｊｋ  
param  
double alpha: ロボットの中心から駆動輪までの極座標の角度（前方をｙ座標正にして）【deg】  
double r:ロボットの中心から駆動輪までの極座標の距離[m]  


pub  
[left_front](chjk/unit_cmd)：左前のロボット座標でのステア・駆動指令[rad][m/s]  
[right_front](chjk/unit_cmd)：右前のロボット座標でのステア・駆動指令[rad][m/s]  
[left_rear](chjk/unit_cmd)：左後のロボット座標でのステア・駆動指令[rad][m/s]  
[left_rear](chjk/unit_cmd)：左後のロボット座標でのステア・駆動指令[rad][m/s]  

sub
[pose](geometry_msgs/Pose2D):グローバル座標での姿勢位置[m][rad]
[cmd](chjk/vw_cmd):グローバル座標での速度指令[rad/s][m/s]


#chjk_odometry  

	1.chjk_odometry_node
	param
	double enc_per_m: エンコーダが１ｍあたりに増加するエンコーダ数

	pub
	[tf](tf/Message):ロボットのフレームを/base_link,オドメトリ座標フレームを/odomとしてその間の移動、回転の情報


	sub
	[enc](std_msgs/Int64):自己位置推定用のエンコーダの値
	[gyro_pose](std_msgs/Int16):ジャイロによって推定した姿勢の値[deg]
	[cmd](chjk/vw_cmd):グローバル座標での速度指令[rad/s][m/s]




	2.pose_estimate_out_node

	pub
	[pose](geometry_msgs/Pose2D):グローバル座標での姿勢位置[m][rad]

	sub
	[tf](tf/Message):ロボットのフレームを/base_link,グローバル座標フレームを/mapとしてその間の移動、回転の情報



#joy_controller  
param  
double MAX_VEL: ロボットの最大速度[m/s]  
double MAX_ANGULAR_VEL:　ロボットの最大角加速度[rad/s]  

pub  
[cmd](chjk/vw_cmd):グローバル座標での速度指令[rad/s][m/s]  

sub  
[joy](sensor_msgs/Joy): joyコントローラの入力  
＊左スティックでｘｙ座標の速度、左スティックの右半面、正の回転、左反面、負の回転  







