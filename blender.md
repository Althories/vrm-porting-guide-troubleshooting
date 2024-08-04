## This file contains troubleshooting fixes for the process in current Blender and Blender 2.79.

### >---------- NEW BLENDER ----------
Q1: When I reopened by blend file, my model's untextured and bright pink!

> A1: That happens because the textures aren't packed into the .blend file, so reopening the project will have those textures missing. While it can be off-putting and harder to work with, it does not affect the process.

Q2: When I'm trying to export with bodygroups, I get an error along the lines of "too many 96 flex controllers on x".

> A2: AFAIK, a model can have up to 96 flex controllers. You may have more than 96, or you may have combined and re-separated parts of the model such that separate parts both have flexes (ex. the body mesh has flexes.) This puts the flex controller count over the limit, so you must ensure flexes (shape keys in blender) are only present on the face mesh, where they're used.

### >---------- 2.79 BLENDER ----------
Q3: RuntimeError: Armature 'proportions' not in edit mode, cannot add an editbone

> A3: When you're importing the .smd, make sure to first set 'Bone Append Mode' to 'Make New Armature', then import the following model pieces with 'Append to Target'.

Q4: When I import my model, the skeleton is much smaller than the model's mesh.

> A4: In new Blender, apply all transformations (with Ctrl+A) on everything in the scene. Then, re-export the model.
