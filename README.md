# Mechanics-track3
#### Calculate Forward and Inverse kinematics for a robot with 3 degrees of freedom
##### Forward kinematics:
###### we will determine the position and direction of the end effector by looking at the joint angles of the three joints
##### In general:
###### -Define the reference frames for each joint using the Denavit-Hartenberg (DH) convention.
###### -Compute the transformation matrices between each adjacent frame.
###### -Multiply the transformation matrices to get the overall transformation from the base frame to the end-effector frame.

#### Define DH parameters

```
i1, i2, i3 = link lengths
j1, j2, j3 = link offsets
θ1, θ2, θ3 = joint angles
```

#### Compute transformation matrices

```
T01 = [[cos(θ1), -sin(θ1), 0, i1*cos(θ1)], 
       [sin(θ1),  cos(θ1), 0, i1*sin(θ1)],
       [0, 0, 1, j1],
       [0, 0, 0, 1]]

T12 = [[cos(θ2), -sin(θ2), 0, i2*cos(θ2)],
       [sin(θ2),  cos(θ2), 0, i2*sin(θ2)], 
       [0, 0, 1, j2],
       [0, 0, 0, 1]]

T23 = [[cos(θ3), -sin(θ3), 0, i3*cos(θ3)],
       [sin(θ3),  cos(θ3), 0, i3*sin(θ3)],
       [0, 0, 1, j3], 
       [0, 0, 0, 1]]
```

#### Compute the overall transformation

```
T03 = T01 * T12 * T23
```





