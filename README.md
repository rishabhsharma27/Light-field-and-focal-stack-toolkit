We have build on the work of Katrin Honauer & Ole Johannsen who have developed the multi-camera based light field rendering blender model.
We add an focal stack rendering model to their existing Light field blender model to allow researcher generate the focal stack for the same light field scene. 
Since we have build on the work of Katrin Honauer & Ole Johannse, we have kept the description of their work as it is in the readme file.(this file)

# Installation of light field and focal stack model (installation remains the same as we have added the focal stack as an addon to the light field model)

Please clone the git repository into the blender/VERSION/scripts/addons/ folder of your local blender installation.
Afterwards, you can activate the add-on at File -> User Preferences -> Add-ons -> Render.
Once activated, the add-on can be found at the left menu of the '3D View' window at 'Misc'.


# Usage focal stack model (Our work)

The model lets the user create a focal stack with different camera parameters that include the focal length, image resolution, sensor size, and f-stop number.

In addition to the camera parameters, the user has an option to enter the number of images they need in the focal stack. 
The number of images required for the focal stack determines the focus point for the camera for each image in the focal stack. 

We use the disparity values from the light field camera parameters and the number of images to create focus points at equal intervals in the z-plane. 
The disparity values differ from the depth values used to select the focal point. 


# License Focal stack model (Our work)

Authors: Rishabh Sharma, Eva Cheng & Stuart Perry.

@article{sharma2022noise,
  title={Noise-Resilient Depth Estimation for Light Field Images Using Focal Stack and FFT Analysis},
  author={Sharma, Rishabh and Perry, Stuart and Cheng, Eva},
  journal={Sensors},
  volume={22},
  number={5},
  pages={1993},
  year={2022},
  publisher={MDPI}
}


# Usage LF model

You can generate a new camera grid using the 'Add Camera Grid' button. Any changes to the parameters of the camera grid will be updated instantaneously. For better visualization, we added a frustum that shows the volume that is covered by the light field for a given disparity range. As described in the additional material of our paper, the camera grid is focused on a certain plane. 

Please note, the cameras are shifted, not rotated, so the optical axes are still parallel! If you want to generate a camera grid which is focused at infinity, i.e. has non-shifted identical cameras, you can set the focus distance to 0.

To render the scene, press the 'Render Light Field' button. It will render all views to the given directory using the renderer and the render settings you have chosen. For depth/disparity map generation the add-on switches to the internal blender renderer. There are two reasons for this behavior. First, it is much faster than the e.g. cycles renderer and better suited to generate high resolution depth maps. Second, different renderer have different interpretations of depth. The internal renderer computes the distance in Z direction, while cycles computes the Euclidean distance. To bypass knowing all potential renderer we fall back to the ubiquitous blender renderer.

# License LF model
This work is licensed under the Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License. 
To view a copy of this license, visit http://creativecommons.org/licenses/by-nc-sa/4.0/. 
 
Authors: Katrin Honauer & Ole Johannsen 

Website: www.lightfield-analysis.net 

 
This add-on is based upon work of Maximilian Diebold. 

The 4D Light Field Benchmark was jointly created by the University of Konstanz and the HCI at Heidelberg University. If you use any part of the benchmark, please cite our paper "A dataset and evaluation methodology for depth estimation on 4D light fields". Thanks! 
 
 @inproceedings{honauer2016benchmark, 
 title={A dataset and evaluation methodology for depth estimation on 
 4D light fields}, 
 author={Honauer, Katrin and Johannsen, Ole and Kondermann, Daniel 
 and Goldluecke, Bastian}, 
 booktitle={Asian Conference on Computer Vision}, 
 year={2016}, 
 organization={Springer} 
 } 



 


