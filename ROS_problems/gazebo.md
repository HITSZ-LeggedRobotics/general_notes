# Contact Sensor
**reason**:Wrong collision flag
> You can check on your own with editing an urdf from a xacro (rosrun xacro xacro.py -o robot.urdf robot.xacro) and then a sdf from an urdf (gz sdf -p robot.urdf > robot.sdf), you will see that the issues are with the collision flags, both the one inside the gazebo link and the one inside the link. [LINK](http://answers.gazebosim.org/question/15095/gazebo-contact-sensor-added-to-a-robot-link-in-urdf-file-is-not-working-as-expected/)
