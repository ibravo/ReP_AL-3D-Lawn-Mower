ReP_AL 3D Printed Robot Lawn Mower
----------------------------------

Mega_V9.7 Details
----------------------

Mega_V9.7.ino
Load_EEPROM_Saved_Data()

DisplayTime_DS1302()


--------------------
Bumpers.ino
--------------------
// Routine to check the bumper Switch
// The global variable Bump is then activated so the Mower can react to the bumper being activated
Check_Bumper()


--------------------
Manouvers.ino
--------------------
// Manouvers are a set of motion functions or motor actions that are regulary called
// e.g. Turn the mower around

// void Manouver_Mow_The_Grass()      normal grass cutting operation 
// void Manouver_Aerate_The_Grass()   aeration process
// void Manouver_Find_Wire_Track()    Finds the wire edge before tracking the wire
// void Manouver_Turn_Around()        How the mower eacts when corssing the wire
// void Manouver_Turn_Around_Sonar()  Hoe the mower avoids a sonar obstacle

// void Manouver_Manuel_Mode()
// void Manouver_Start_Mower()
// void Manouver_Mower_Exit_Dock()
// void Manouver_Dock_The_Mower() 
// void Manouver_Park_The_Mower_Low_Batt()
// void Manouver_Park_The_Mower()
// void Manouver_Hibernate_Mower()

// void Manouver_Go_To_Charging_Station()     Starts the sequence to send the mower to the charge station
// void Manouver_Exit_To_Zone_X()             Brings the mower out of the dock and tracks the wire to the start zone

// Moves the Mower Forwards in the garden and activates compass features if enabled





--------------------
Motor_Action_Mower.ino
--------------------
// Motor Bridge pins are set for both motors to move forwards
SetPins_ToGoForwards()

// Motor Bridge pins are set for both motors to move backwards
SetPins_ToGoBackwards()

// Motor Bridge pins are set for both motors to stop
Motor_Action_Stop_Motors()

// Pins are set so that Motors drive in opposite directions
SetPins_ToTurnLeft()

// Pins are set so that Motors drive in opposite directions
SetPins_ToTurnRight()

// USed to turn the mower at a set speed.
Motor_Action_Turn_Speed()

//Steers the Mower depending on the PID input from the Algorythm
Motor_Action_Dynamic_PWM_Steering()

// Turns the mowing blades on or off
Motor_Action_Spin_Blades()
Motor_Action_Stop_Spin_Blades()

// Adjusts wheel speed according to the MAG level
Motor_Action_Go_Mowing_Speed()

    // Full straighgt speed no motr speed ramp up.
    Motor_Action_Go_Full_Speed()
    // Slow straighgt speed no motr speed ramp up.
    Motor_Action_Go_Slow_Speed()

//Speeds can be changed to give the mower a slight curve when exiting the Garage.
Motor_Action_GoFullSpeed_Out_Garage()









--------------------
Sonar.ino
--------------------
// Ping Sonar sensors
Check_Sonar_Sensors()


--------------------
Wheel_Amps.ino
--------------------
// Calculate Amp Value from Wheel Amp sensor
Calculate_Wheel_Amps()

Check_Wheel_Amps()
Test_Check_Wheel_Amps()


--------------------
Wire_Detection.ino
--------------------

// Check the mower is inside (0) or outside (1) the perimeter wire
void Check_Wire_In_Out()

//Check that boundary wire is turned on
void Running_Test_for_Boundary_Wire()

UpdateWireSensor()
PrintBoundaryWireStatus()
Run_Initial_Boundary_Wire_Test()


--------------------
Wire_Tracking.ino
--------------------

//  Prints a visual display of the wire tracking in the Serial Monitor
//  to see how well the wire is being followed.  Adjusting the P value in the settings
//  can improve the wire tracking ability of the mower.
PrintWirePosition()

// Function to follow the wire for a specific amount of time set by the itterations 'I'
// Robot tracks the wire until the itterations are exhausted.
Track_Wire_From_Dock_to_Zone_X()

//  Track the Perimeter wire using a PID type method
//  This code tracks the boundary wire and by calculating the Perimeter Magnitude and calculating the distance to the center of the wire.
//  This error value of (position - center of wire) is mulitplied by the P value in the setup to send a PWM change to the left or right
//  wheel to bring the sensor back over the wire.*/
Track_Perimeter_Wire_To_Dock()

//Starts an algorithym to find the wire again after it is lost in tracking
void Tracking_Restart_Blocked_Path()

