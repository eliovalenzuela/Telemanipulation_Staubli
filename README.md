# Telemanipulation_Staubli
Robotic cell project developed on Staubli Robotic Suite 2022.7 for the TX2-90 model and CS9 controller. It uses the official "alter" addon to modify on real-time the trajectory of the tool (this is the only way to input high frequency trajectories to the CS9 controller). The target position of the tool is sent via UDP socket at 100Hz. The message contains positions (X, Y, Z) and rotations (RX, RY, RZ). The program consist of: 
- 1 task for initialization
- 3 asynchronous tasks for I/O, movement control and communications
- 1 synchronous task to manage the force sensor functions

  <img width="462" height="313" alt="image" src="https://github.com/user-attachments/assets/398c0339-5291-494d-bbd5-069c834bb0fd" />

The system provides three main operating modes:
- Manual control allows the user to command each of the six joints individually by selecting their target angles.
- Tool Change mode executes predefined sequences for parking and mounting tools, including approach, contact detection and pneumatic coupling.
- Haptic mode enables real-time control from an external device and includes three sub-modes: The Fast and Precise sub-modes adjust the motion scaling between the haptic device and the robot to allow either larger or finer movements. A third sub-mode enables guided manipulation, where the user physically pulls the robot’s wrist and the system interprets the forces measured by the F/T sensor to reposition the robot, supporting intuitive teaching and range checking.

The program requires to run the associated Unity3D scene to receive inputs and work properly.
<img width="900" height="691" alt="image" src="https://github.com/user-attachments/assets/15e8b9fe-1246-458f-9203-6f5b447697c0" />
