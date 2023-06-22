Automatically Extract 3D pose from egocentric view images

## Environment Setup 
  > conda create --name hand3d_env python=3.7\
  > conda activate hand3d_env\
  > conda install -c conda-forge opencv\
  > conda install pytorch torchvision torchaudio cudatoolkit=10.1 -c pytorch 

install Mano model

https://github.com/hassony2/manopth and move the root folder into "models/MANO_layer". The "setup.py" file should be located at "models/MANO_layer/manopth/setup.py". To install, navigate to the same directory "setup.py" is located in and run

  > pip install .


## Usage

### Just run pose_annotator.py file in command. The Gui setup will be started. 
Just Click Auto button !
The YOLO will predict bounding box of the hand. And extract 2d, 3d pose by resnet and Hrnet



### Saving
To save the hand pose, click the "Save" button, which will save the MANO parameters, 3D global joint locations and 2D image joint locations in the same directory for the input images.

  * MANO file

This ndarray contains 51 values. The first 3 values contain the global 3D root joint location (x: increases going right. y: increases going down. z: increases going away from camera origin). The next 3 values contain the global orientation for the hand pose (rotational values for the root joint). The remaining 45 values contain rotations for 15 hand joints (finger tip does not have a rotation).

  * 3D Global Keypoints file

This ndarray has shape of [21, 3], which contains the 3D global joint location (in cm) for all 21 joints.

  * 2D Global Keypoints file

This ndarray has shape of [21, 2], which contains the 2D joint location ((row, col) in percentages, so they are invariant to image scaling) for all 21 joints. 



### The Readme file will be update soon. If you have question about this project. Please feel free to send me an email 
email : 99xtaewoo@gmail.com

