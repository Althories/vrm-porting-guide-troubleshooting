## This file contains troubleshooting fixes for problems after successful model compilation. For the most part, refer to Crowbar documentation for compilation errors.

### >---------- GENERAL ----------

Q: Crowbar compilation error: could not load file 'anims/reference_female'"

> A: This can occur if you don't set the correct file path to export to in old blender. Redo proportion trick or set the export directory to the correct folder (proportion trick compile)

Q: Crowbar compilation error: Stack Overflow Error during compilation OR "Ghost Compile"

> A: This may occur if your model's polycount is too high. You may also have this issue if Crowbar says your model compiled, but there is no output. Another reason this may occur is if you are targeting the wrong .dmx file or using the wrong .qc file. FIRST, try adding "$maxverts 65536" below the $ambientboost line in the .qc, then recompiling. If that doesn't work, try removing parts of the mesh or using other methods to reduce your model's overall polygon count. You can reduce your polygon count in the model export settings of vroid studio, which I highly recommend. Blender's decimate modifier can also reduce polygon count. Be warned though: the decimate modifier is not able to apply to the face without removing its shape keys. If you wanted to keep shape keys, try applying the decimate modifier to mesh parts BEFORE joining them with the face. I THINK that the threshhold for Crowbar's polygon limit is 25-30k, but don't take my word for it.

Q: Crowbar compilation error: Too many bone influences per vertex

> A: This may occur if you used the decimate modifier in 2.79 Blender. You can press 'Space' to search Limit Number of Weights per Vertex. Lower all parts of your mesh to 3 or below, then re-export the model. 2.79 Blender may still give an export warning, so you can keep lowering the limit until the warning goes away. I'm hoping this does not have disastrous consequences outside of my test run

Q: My model compiled, but there is nothing in the compilation log to suggest it was actually processed

> A: Redo proportion trick. There may not have been anything put into the generated 'anims' folder inside the proportion trick compile folder, so you will need to redo/re-export via proportion trick

Q: My model compiled, but its limbs are all stretched out!

> A: This is a result of using the pre-proportion trick model smd. Make sure you used the model dmx from your proportion trick export.

Q: My model compiled, but it's stuck in a T-pose!

> A: It's likely that the skeleton wasn't properly identified by Crowbar. You may have forgotten to rename the bones, or there was a misstep during proportion trick. Checking for the first is easy,
but knowing whether you messed up in proportion trick can be tough to determine. If that might be the case, I would recommend re-exporting your model from new Blender and re-applying proportion trick.

Q: When I apply my model in the playermodel selector, my model appears as an error.

> A: If you think everything else is right and your model looks normal in Crowbar's model viewer, you likely have a typo or incorrect directory in the .lua file. That, or one of the lines is commented out. True story!

### >---------- RAGDOLL ----------

Q: The ragdoll for my model has verticies stretching the mesh in unnatural directions.

> A: The usual reason for this is because not all bones were properly handled in either renaming, proportion trick, or a combination of the two. Checking whether you missed renaming bones or just re-applying proportion trick can fix the issue.

Q: The ragdoll for my model is colliding improperly with itself and causing odd collision behavior.

> A: Redo your collision model smd in current Blender. If you used the optional method of ragdoll model creation, it's possible you made parts of the collision model overlap, which, unsurprisingly, can lead to unusual collision behavior.

Q: The toe/foot bones on my radgoll are indented into the mesh!

> A: This stems from a misstep in proportion trick, particularly the part involving rotation of the foot and toe bones. Time to redo proportion trick!

### >---------- VIEWMODEL ARMS ----------

Q: My viewmodel arms look all crunchy and malformed in-game!

> A: Make sure to use the post-proportion trick model smd when you're importing to make the arms. Using the arms in the compile template folder rather than the proportion trick compile folder will cause this mesh deformation.

Q: My viewmodel arms are blocking part or all of my pov!

> A: You'll need to delete some more of the c_arms mesh in Blender that's closer to where the head would be. If there are any parts that point inwards towards the head, there's a chance they'll obstruct your view.
