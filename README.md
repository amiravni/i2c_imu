i2c_imu
=======

ROS driver for several 9-DOF IMUs.  This node is a ROS interface for [RTIMULib2](https://github.com/RTIMULib/RTIMULib2) by [richards-tech](http://richardstechnotes.wordpress.com/), a C++ library of drivers & filters of operating I2C IMUs in linux.  I take no credit for RTIMULib (the hard part), I simply created a ROS interface to it (the easy part).

The list of IMUs supported by RTIMULib is as follows:

- [MPU-9150 by Invensense](http://www.invensense.com/mems/gyro/mpu9150.html)
- [MPU-9250 by Invensense](http://www.invensense.com/mems/gyro/mpu9250.html)
- [LSM9DS0 by STMicroelectronics](http://www.st.com/web/en/catalog/sense_power/FM89/SC1448/PF258556)
- [Adafruit 9-DOF IMU Breakout - L3GD20 + LSM303](http://www.adafruit.com/product/1714)
- [MinIMU-9 v3 Gyro, Accelerometer, and Compass (L3GD20H and LSM303D Carrier) by Polulu](http://www.pololu.com/product/2468)




## Making it work on odroid C2

1. Clone i2c_imu package, extract to ~/catkin/src/
2. Clone [RTIMULib2](https://github.com/RTIMULib/RTIMULib2)
3. Compile [RTIMULib2](https://github.com/RTIMULib/RTIMULib2) according to [this Readme](https://github.com/RTIMULib/RTIMULib2/tree/master/Linux)
4. Move the [RTIMULib](https://github.com/RTIMULib/RTIMULib2/tree/master/RTIMULib) source folder to ~/catkin/src/i2c_imu/
5. Move the [RTIMULib](https://github.com/RTIMULib/RTIMULib2/tree/master/Linux) compiled folder (under /build/) to the ~/catkin/devel/lib/i2c_imu/
6. Add RTIMULib to include_directories under the [CMakeLists.txt](https://github.com/jeskesen/i2c_imu/blob/master/CMakeLists.txt) file 
7. Compile the i2c_imu package ("Catkin_make")
8. roslaunch the [launch file](https://github.com/jeskesen/i2c_imu/blob/master/launch/i2c_imu_auto.launch)

