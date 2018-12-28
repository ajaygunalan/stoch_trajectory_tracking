### Problems with IMU

1. The MPU 9150 with RTIMU library (python) is drifing a lot when used in RPI3

#### Approach

 1. Test another IMU with arduino using (https://kingtidesailing.blogspot.com/2015/09/how-to-setup-mpu-9150-9-axis.html) to check if that is the same case here too.  (Download the libraries and check the BAUD RATE)

 2. Follow [this link](https://www.instructables.com/id/Simple-Manual-Magnetometer-Calibration/) for testing and calibration with RPI3. (Tutorial Not Clear -*Vague*)
 
 3. Works well with [this repo](https://github.com/mrbichel/linux-mpu9150)
 
#### Status

1. ~~Following this repo~~  (https://github.com/blauret/RTIMU) 

   a. RTIMU GUI for Calibration is cool...!
   
   b. On Hold -> Check the Python interface values.

2. Follow this repo (https://kingtidesailing.blogspot.com/2016/02/how-to-setup-mpu-9250-on-raspberry-pi_25.html)

   a. Seems easier
   
   

#### Next

1. To make sure the imu works with main code in Python so that we could interface the existing `stoch` libraries
2. Estimation of x,y and orientation from IMU and UWB.
3. Implementation of controls heuristics to follow a staright line.


#### Questions

1. Why IMU calibration is needed ?

#### Tips

1. Check if IMU is connected on I2C line by `i2cdetect -y 1` or `i2cdetect -y 0` . If you see a output like below, it's connected:

```
     0  1  2  3  4  5  6  7  8  9  a  b  c  d  e  f
00:          -- -- -- -- -- -- -- -- -- -- -- -- -- 
10: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
20: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
30: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
40: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
50: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
60: -- -- -- -- -- -- -- -- 68 -- -- -- -- -- -- -- 
70: -- -- -- -- -- -- -- -- 
```
2. Check if i2c is enabled by `dmesg | grep i2c`

3. Don't use I2C for distance more than foot.

4. IMU is prone to interference by ferrous metal.


#### Reference
1. https://arduino.stackexchange.com/questions/31552/mpu-6050-angle-drift
2. https://www.novatel.com/assets/Documents/Bulletins/APN064.pdf
3. "A robust and easy to implement method for IMU calibration without external equipments"

  Added on 17/12/2018 (dd/mm/yyyy)
  
1. https://github.com/kriswiner/MPU6050/wiki/Affordable-9-DoF-Sensor-Fusion (Theory)
2. https://github.com/kriswiner/MPU9150 (Theory)
3. https://github.com/kriswiner/MPU6050/wiki/Simple-and-Effective-Magnetometer-Calibration (Theory)
4. https://www.instructables.com/id/Simple-Manual-Magnetometer-Calibration/ (Tutorial)
5. I2c Reference (https://www.raspberrypi-spy.co.uk/2014/11/enabling-the-i2c-interface-on-the-raspberry-pi/) (enable I2C on rpi3)
6. https://github.com/vmayoral/bb_mpu9150/blob/master/src/linux-mpu9150/README.md (ROS Package)
7. https://github.com/mrbichel/linux-mpu9150 (Proper C++ repo for MPU-9150)

 Added on 26/12/2018 (dd/mm/yyyy)
 
 1. Integrated all in one package [BNO55](https://www.bosch-sensortec.com/bst/products/all_products/bno055)
