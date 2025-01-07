# Tasks


## Road Following Algorithm Development

- **Algorithmic Foundation:** The core of your task is to develop an algorithm that enables a simulated robot to follow a designated path. You may opt for various approaches such as sensor-based line following, computer vision techniques, or even basic AI algorithms.

- **Sensor Integration:** Utilize the simulated vision sensors in CoppeliaSim to detect the path.

- **Control Logic:** Develop the control logic that translates sensor input into motor commands.
This could involve simple steering mechanisms or more complex control systems like PID controllers.

- **Programming:** Write your algorithm in Python, ensuring it interfaces effectively with CoppeliaSim through the Remote API. Focus on writing clean, well-documented code for ease of understanding and modification.
Key Concepts and Approaches:

    - **Computer Vision:** Explore image processing techniques like color detection, edge detection, or even neural networks for more advanced implementations.

    - **Proportional Control:** For simpler paths, a proportional controller might suffice to adjust the robot's steering based on the deviation from the path.

    - **Debugging and Iteration:** Regularly test your algorithm in the simulation. Be prepared to iterate and debug based on the robot’s performance.

## Task 1

Implement the get_handles method. Objective of this method is to retrieve and store handles for various robot components (left motor, right motor, camera) using CoppeliaSim's API. Hint: Use sim.simxGetObjectHandle for each component (left motor, right motor, and camera). Store the retrieved handles in corresponding class attributes.


## Task 2

Implement get_image Method which captures an image from the robot's vision sensor, processes it into a grayscale format, and applies thresholding to identify relevant features. Use CoppeliaSim's vision sensor API to retrieve the image and its resolution. Convert the captured data into a format suitable for further processing. Transform the raw image data into a 3D array format that represents the image dimensions (height, width, color channels). Ensure the reshaped image retains the appropriate color channels. Return the thresholded image.

## Task 3

Implement the process_image Method to identify the Road's Centroid. Use an image processing library (e.g., OpenCV) to compute the moments of the binary image. Image moments provide statistical properties that describe the shape and distribution of the white pixels. If the centroid is valid, return its x, y coordinates. If no centroid is detected, return None.

## Task 4

Implement the calculate_steering_angle Method. Compute the steering angle based on the deviation of the road centroid from the image center. Determine the difference between the road centroid and the image center. Normalize this difference by dividing it by the image center value. This error difference represents how far the road is from the ideal central position. Return the normalized steering angle.

## Task 5

Implement the handle_camera Method to Steer the Robot which is a function that integrates image processing and control logic to steer the robot based on the road's position detected in the camera feed. Capture the image(use the provided get_image method), determine the centroid and then calculate the steering angle (use the provided steer Method). Steer the robot based on the computed steering angle using the steer method.

## Task 6

Implement the steer Method. Adjust the robot's left and right motor speeds based on the calculated steering angle. Compute the left and right motor speeds using the steering angle and base speed. Ensure the robot steers smoothly.

## Task 7

Implement the set_wheels_speed Method. Control the speed of the robot's left and right motors by interfacing with CoppeliaSim's API.

 

## Task 8

Implement the stop Method. Stop the robot by setting motor speeds to zero. Call set_wheels_speed with both speeds set to 0. Ensure the robot halts.


