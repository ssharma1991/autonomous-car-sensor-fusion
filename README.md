# Object Tracking using Extended Kalman Filter for Self-Driving Car

In this project an extended kalman filter is used to estimate the state of a moving object of interest by fusing noisy lidar and radar measurements. The predicted readings are compared to ground truth readings to get insights into quality of prediction. Finally, the realtime prediction of moving object has is visualised in simulator environment which communicates with the c++ program using ``uWebSocketIO``.

![Object Tracking using EFK](Results/EKF_data1.gif)

The main program files are in ``src`` folder and include the following files:
* ``main``: Communicates with the simulator, recieves RADAR and LIDAR data and predicts state using ``FusionEKF`` class
* ``FusionEKF``: contains routines which initializes the kalman filter variables and carries out prediction and update using Simple Kalman or Extended Kalman filter depending on LIDAR or RADAR data respectively using ``kalman_filter`` class.
* ``kalman_filter``: contains equations to carry out prediction and update steps.
* ``tools``: contains code to calculate rmse error and Jacobian matrices.
* ``measurement_package``: contains defination for class used to store LIDAR or RADAR measurement data


The project can be built and run by doing the following from the project top directory.

1. mkdir build
2. cd build
3. cmake ..
4. make
5. ./ExtendedKF

Within the Simulator environment, Project 1 simulates a car moving on a tilted 8 shape track. Its trajectory is tracked using noisy RADAR and LIDAR readings. Two datasets are available in the simulator. The blue and red dots represent RADAR and LIDAR measurements while the green dots represent predictions made by Extended Kalman Filter algorithm.

![Object Tracking for Dataset 1](Results/Dataset1.PNG)

![Object Tracking for Dataset 2](Results/Dataset2.PNG)

The final RSME error vector [px,py,vx,vy] for dataset 1 is [.097,.086,.451,.440] while for dataset 2 is [.073,.097,.458,.500].These are within the tolerance limits specified as [.11, .11, 0.52, 0.52].

## References
This project is submitted as partial fulfillment of the Udacity's Self-Driving Car Engineer Nanodegree program. The helper code is available [here](https://github.com/udacity/CarND-Extended-Kalman-Filter-Project).