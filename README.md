#Motivation
MuJoCo scene construction lacks a convenient 3D GUI you can use to compose hierarchies, edit meshes, or add elements. Although Blender is not a proper CAD software it is really smooth to extend with scripts, and quickly align a scene. 


#Installation
Add the script through Preferences > Add-ons > Install...


#Usage
Parented mesh objects will be converted into body hierarchies in the MJCF file. The only elements apart from bodies and mesh geoms so far are sites, hinge joints and free joints. They are all interpreted from "Empty" objects in the scene. Sites should have "site" in their name. Joints should have "joint" in their name, and hinge joints should use the "single arrow" type, freejoints should use "plain axes".

It is recommended to reset the origin of child objects so they align with their DOFs' location and principal axis. This will make the generated MJCF easier to read and more precise.

Select the root body, go to File > Export > MJCF (.xml), and enable the "Selected Only" option. Navigate to the location you want to save your file, then click Export MJCF. A new directory will be created where meshes will be exported to.

The expectation is that the generated file will be further edited by user to add necessary joints, tendons, etc.

#Planned features
Feel free to send pull requests. Reasonably straightforward additions would be:
- Support slider and ball joints
- Add option in export operator to automatically add a freejoint to the root body
- Add option in export operator to define precision level of numbers
- Add option for empty bodies, and primitve geoms