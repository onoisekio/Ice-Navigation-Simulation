# Ice-Navigation-Simulation
This is Matlab/Unreal Engine 4.26 simulation of a Sim3d UAV coorperating with a Sim3d autonomous surface ship (MASS) to facilitate the MASS's navigation in ice.
The UAV performs survey missions to gather and process ice data. Safe navigation paths for the MASS are estimated from the processed data and represented in a colour-coded hazard map.
Simulation must be run on MATLAB V. 2022a and Unreal Engine 4.26. See below for instructions to run the simulation on MATLAB. Contact Gerald Kio @ zckog@yahoo.com for more information. 

Simulation Instructions
1.	Launch MATLAB V. 2022a
2.	Change working path to MatlabSim if necessary 
3.	Launch Simulink 
4.	Launch MASS_Simulation.slx located in the working path
5.	Double-click on the Simulation 3D Scene Configuration2 Simulink block and make selections in its Block Parameters dialogue box.
6.	Select the (UE) Project DroneExp1.uproject   
7.	Click Open Unreal Editor to launch UE Editor
8.	Click Apply and OK to close the dialogue box
9.	After UE Editor launches, click Run on Simulink editor to start the simulation. Wait for it to compile, and when ready click Play on UE Editor to start the simulation
10.	Maximize Matlab windows docked in the tray to view the simulation.
![image](https://github.com/user-attachments/assets/4170ac6c-9b61-4de5-9e13-cd08703967e8)

Simulation & Helper Scripts (MatlabSim\MatlabSim\...)
1.	SimEnvironment.mat – Contains simulation presets for the simulation vehicles and shipping environment  
2.	LeftRiverGeoPts.mat, RightRiverGeoPts.mat – Estimates of geocoordinates of shipping boundaries
3.	OccMap.mat – contains default pixel and geocoordinates, and colours of hazard map points
4.	ShipPath.mat – Calculated ship path
5.	Run0, 1, 2, 3.mat – Parameters for Hazard-Uncertainty experiment 
6.	OccupancyMap.mat – Default occupancy map
7.	SimulationControl.m – Implements a system state machine 
8.	PathPlanSubsystem.m – Calculates survey paths for the drone and travel paths for the ship with the RRT algorithm
9.	ImageProcessingSubsystem.m – Processes images obtained by the drone camera to produce ice concentration data
10.	LidarProcessingSubsystem – Processes LiDAR range data to produce Ice Multipliers
11.	DataFusionSubsystem – Processes outputs from ImageProcessing (4) and LidarProcessing (5) functions to update ice numerals, occupancy, and hazard maps
12.	RGBToGray – Converts RGB image data to grayscale 
13.	HazardMapDisplay – Displays the drone, ship positions and paths on the Hazard map
14.	DistributeIceXML1.m (FuzzyBlockSegmentation, GenerateIcePatches) – Calculates distribution of ice in the shipping environment
15.	exampleHelperCheckIfGoal.m – Helper function for the RRT algorithm
16.	MatlabUnrealVehicleConfig – Script to install required MATLAB plugins into Unreal Engine. Probably outdated. Check MathWorks website for updates
17.	IceConcentrations.xml – Ice distribution input to Unreal Engine simulation
