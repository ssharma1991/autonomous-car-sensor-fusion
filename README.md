# Extended Kalman Filter for Self-Driving Car

In this project an extended kalman filter is used to estimate the state of a moving object of interest by fusing noisy lidar and radar measurements. The predicted readings are compared to ground truth readings to get insights into quality of prediction. Finally, the realtime prediction of moving object has is visualised in simulator environment which communicates with the c++ program using ``uWebSocketIO``.

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

Within the Simulator environment, Project 1 simulates a car moving on a tilted 8 shape track. Its trajectory is predicted by inputting noisy RADAR and LIDAR readings. Two datasets are available in the simulator. The blue and red dots represent RADAR and LIDAR measurements while the green dots represent predictions made by Extended Kalman Filter algorithm.

The final RSME error vector for dataset 1 is [.097,.086,.451,.440] while for dataset 2 is [.073,.097,.458,.500].These are within the tolerance limits specified as [.11, .11, 0.52, 0.52].

