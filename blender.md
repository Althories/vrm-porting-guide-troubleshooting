## This file contains troubleshooting fixes for the process in current Blender and Blender 2.79.

### >---------- NEW BLENDER ----------
Q1: When I reopened by blend file, my model's untextured and bright pink!

> A1: That happens because the textures aren't packed into the .blend file, so reopening the project will have those textures missing. While it can be off-putting and harder to work with, it does not affect the process.

Q2: When I'm trying to export with bodygroups, I get an error along the lines of "too many 96 flex controllers on x".

> A2: AFAIK, a model can have up to 96 flex controllers. You may have more than 96, or you may have combined and re-separated parts of the model such that separate parts both have flexes (ex. the body mesh has flexes.) This puts the flex controller count over the limit, so you must ensure flexes (shape keys in blender) are only present on the face mesh, where they're used.

### >---------- 2.79 BLENDER ----------
Q3: RuntimeError: Armature 'proportions' not in edit mode, cannot add an editbone

> A3: When you're importing the .smd, make sure to first set 'Bone Append Mode' to 'Make New Armature', then import the following model pieces with 'Append to Target'.

Q4: UnicodeDecodeError: 'utf-8' codec can't decode byte 0xd5 in position 0: unexpected end of data

> A4: I don't have complete confirmation just yet, but this might happen if your blender or computer is in a language other than English. Instead of changing the language, something you can try is editing the Blender Source Tools script and making the following change: Change 'return out.decode()' to 'return out.decode(errors="ignore")'. You can find where this script is located by opening Old Blender, going to File > User Preferences > Addons, and finding the Blender Source Tools addon in the list. The description of the addon should tell you where the script is located in your filesystem.

Q5: When I import my model, the skeleton is much smaller than the model's mesh.

> A5: In new Blender, apply all transformations (with Ctrl+A) on everything in the scene. Then, re-export the model.

Q6: ERROR: Cannot export shape keys from "model_name" because it has a 'COLLAPSE' Decimate modifier. Only UnSubdivide mode is supported.

> A6: This may happen if you had to use the decimate modifier, and will disable face flex functionality. This message means you used the modifier on the face, which contains shape keys. The decimate modifier cannot be applied on a mesh with shape keys, so you'll need to remove the face from the selection of the modifier. Separate by selection works for this, but it might be easier to go back to a point where the face, body, and hair were still separate.
