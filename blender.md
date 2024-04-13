## This file contains troubleshooting fixes for the process in current Blender and Blender 2.79.

---------- NEW BLENDER ----------
Q1: When I imported the sample collision model, it's in A-pose when it should be in T-pose.

> A1: You're using the sample collision file provided in Deadwater's resources. Use the sampleA or sampleC collision model smds instead, as those are in T-pose.

---------- OLD BLENDER ----------
Q2: RuntimeError: Armature 'proportions' not in edit mode, cannot add an editbone

> A2: When you're importing the .smd, make sure to first set 'Bone Append Mode' to 'Make New Armature', then import the following model pieces with 'Append to Target'.

Q3: When I import my model, the skeleton is much smaller than the model's mesh.

> A3: In new Blender, apply all transformations (with Ctrl+A) on everything in the scene. Then, re-export the model.
