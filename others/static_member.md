2019/01/01
`joint_position_` was declared as a static member, which means it doesn't change with the copy of class, so it always has one value, but is there necessary to use static member? And how to fix it?
