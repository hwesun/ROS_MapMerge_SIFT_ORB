## Introduction
- The project is included in the following paper. The main purpose is for vaildating the map fusion approach. Further details can be found in the paper
### Paper Title: 
- Investigation of SIFT and ORB descriptors for Indoor Maps Fusion for the Multi-agent
### Conference: 
- In The 12th International Conference on Advances in Information Technology (IAIT2021), June 29–July 01, 2021, Bangkok, Thailand.
### Public Organization:
- ACM, New York, NY, USA,
### DOI: 
- https://doi.org/10.1145/3468784.3469950

### Source Map Data:
Map Data is scanned by other teams in Gazebo. It is generated in different time and uses the same 3D model - Willow Garage.

- wg_1: https://github.com/CognitiveRobotics/jarves/tree/master/jarves_gazebo/worlds/maps

- wg_2: https://github.com/Th3CracKed/p3dx_2dnav_simulator/tree/master/p3dx_2dnav/maps/willowgarage

## Environment
### Operation System: Ubuntu *16.04* With ROS Kinetic Dist.
### Python Version: *3.5.2* 
### Jupyter Package Version
- **jupyter-client**                *6.1.11*
- **jupyter-core**                  *4.6.3*
- **jupyterlab**                    *2.2.9*
- **jupyterlab-server**             *1.2.0*

### SIFT in OPENCV:
- To use SIFT descriptor in Python3.5, we need to compile the opencv-contrib library.
- OpenCV Contrib Version: *3.4.2*
- Instructions: https://github.com/opencv/opencv_contrib/tree/3.4

## Usage
- **WithoutMo.ipynp**
  - Find the transformation matrix between two map data without using morphological operation
- **WithMo.ipynp**
  - Find the transformation matrix between two map data with using morphological operation
- It can be used by any map data generated by ROS

## Result
### File Structure

    .                                                 # Setting path in the variable (result_folder)
    ├── org                                           # Generated benchmark map data from wg_1, without rotating and shifting
    |    ├── d0_(percentage)_r.png                    # Reducing benchmark map data - wg_1 overlap area: 100%, 90%, 70%, 50%, 30%
    ├── rot                                           # Generated benchmark map data from wg_2, rotating 90 degrees
    |    ├── d1_(percentage)_r_0_0_0.png             # Reducing benchmark map data - wg_2 overlap area: 100%, 90%, 70%, 50%, 30%
    ├── sift                                          # Result of using sift descriptor
    |    ├── sift_(percentage)_(rotation)_(x_shift)_(y_shift).txt      #export transformation matrix, number of matching points and inliers         
    |    ├── sift_(percentage)_(rotation)_(x_shift)_(y_shift)_org.png  #result of rotating and shifting the map data in rot folder        
    |    ├── sift_(percentage)_(rotation)_(x_shift)_(y_shift)_cmp.png  #figure of SIFT descriptor matching features
    |    ├── sift_(percentage)_(rotation)_(x_shift)_(y_shift)_rot.png  #result of appling transformation matrix on sift_(percentage)_(rotation)_(x_shift)_(y_shift)_org.png
    ├── orb                                           # Result of using orb descriptor
    |    ├── orb_(percentage)_(rotation)_(x_shift)_(y_shift).txt      #export transformation matrix, number of matching points and inliers         
    |    ├── orb_(percentage)_(rotation)_(x_shift)_(y_shift)_org.png  #result of rotating and shifting the map data in rot folder        
    |    ├── orb_(percentage)_(rotation)_(x_shift)_(y_shift)_cmp.png  #figure of ORB descriptor matching features
    └──  └── orb_(percentage)_(rotation)_(x_shift)_(y_shift)_rot.png  #result of appling transformation matrix on orb_(percentage)_(rotation)_(x_shift)_(y_shift)_org.png
