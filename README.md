### Problems with IMU

1. The MPU 9150 with RTIMU library (python) is drifing a lot when used in RPI3

#### Approach

1. Test another IMU with arduino using (https://kingtidesailing.blogspot.com/2015/09/how-to-setup-mpu-9150-9-axis.html) to check if that is the same case here too.  (Download the libraries and check the BAUD RATE)

#### Next

1. If it works then we have to calibrae with RPI3.

#### Questions

1. Why IMU calibration is needed ?


#### Reference
1. https://arduino.stackexchange.com/questions/31552/mpu-6050-angle-drift
2. https://www.novatel.com/assets/Documents/Bulletins/APN064.pdf
3. "A robust and easy to implement method for IMU calibration without external equipments"

  Added on 17/12/2018 (dd/mm/yyyy)
  
1. https://github.com/kriswiner/MPU6050/wiki/Affordable-9-DoF-Sensor-Fusion
2. https://github.com/kriswiner/MPU9150
3. https://github.com/kriswiner/MPU6050/wiki/Simple-and-Effective-Magnetometer-Calibration
4. https://www.instructables.com/id/Simple-Manual-Magnetometer-Calibration/
5. I2c Reference (https://www.raspberrypi-spy.co.uk/2014/11/enabling-the-i2c-interface-on-the-raspberry-pi/)
6. https://github.com/vmayoral/bb_mpu9150/blob/master/src/linux-mpu9150/README.md
7. https://github.com/mrbichel/linux-mpu9150
8. https://github.com/vmayoral/bb_mpu9150
