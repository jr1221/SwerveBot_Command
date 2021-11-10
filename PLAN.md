Things I think are all thats needed to operate the basic example successfully.
 - Drive motor ports
 - Turning motor ports
 - Turning encoder ports, and if reversed?
 - Drive encoder ports, and if reversed?
 - kTrackWidth,  Distance between centers of right and left wheels on robot
 - kWheelBase,   Distance between front and back wheels on robot
 - kGyroReversed, if reversed? **ADXRS450 Gyro must be installed**
 - CHARACTERIZATION CONSTANTS **Full process must be employed, might be able to get away without it as long as using CAN**
 - kMaxSpeedMetersPerSecond, max speed of robot
 - ModuleConstants.kEncoderCPR, counts per revolution, change based on hall pg encoders
 - ModuleConstants.kWheelDiameterMeters, diameter of wheels for distance per pulse (next constant down with encoderCPR)
 - OIConstants.kDriverControllerPort, **xbox port** 


Extra Constants, i.e. no idea what they do or they really dont need to be changed (hoepfully the latter)
- double ModuleConstants.kMaxModuleAngularSpeedRadiansPerSecond = 2 * Math.PI;
- double ModuleConstants.kMaxModuleAngularAccelerationRadiansPerSecondSquared = 2 * Math.PI;
- double ModuleConstants.kDriveEncoderDistancePerPulse =
        **Assumes the encoders are directly mounted on the wheel shafts??**
        (kWheelDiameterMeters * Math.PI) / (double) kEncoderCPR;
- double ModuleConstants.kTurningEncoderDistancePerPulse =
        **Assumes the encoders are on a 1:1 reduction with the module shaft??**
        (2 * Math.PI) / (double) kEncoderCPR;
- double ModuleConstants.kPModuleTurningController = 1;  For profiled PID in turner
- double ModuleConstants.kPModuleDriveController = 1;    For profiled PID in driver
- **Autonomous constants not done**

Hardware needed
- 4 Drive Encoders for CIM
- 4 Turning encoders for PG (come prebuilt, wire via DIO)
- ADXRS450 Gyro (wire via SPI)
