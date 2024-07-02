## This file contains troubleshooting fixes for problems after successful model compilation. Refer to the Crowbar documentation for compilation errors.

### >---------- GENERAL ----------

Q1: My model compiled, but its limbs are all stretched out!

> A1: This is a result of using the pre-proportion trick model smd. Make sure you used the model dmx from your proportion trick export.

Q2: My model compiled, but it's stuck in a T-pose!

> A2: It's likely that the skeleton wasn't properly identified by Crowbar. You may have forgotten to rename the bones, or there was a misstep during proportion trick. Checking for the first is easy,
but knowing whether you messed up in proportion trick can be tough to determine. If that might be the case, I would recommend re-exporting your model from new Blender and re-applying proportion trick.

Q3: When I apply my model in the playermodel selector, my model appears as an error.

> A3: If you think everything else is right and your model looks normal in Crowbar's model viewer, you likely have a typo or incorrect directory in the .lua file. That, or one of the lines is commented out. True story!

### >---------- RAGDOLL ----------

Q5: The ragdoll for my model has verticies stretching the mesh in unnatural directions.

> A5: The usual reason for this is because not all bones were properly handled in either renaming, proportion trick, or a combination of the two. Checking whether you missed renaming bones or just re-applying proportion trick can fix the issue.

Q6: The ragdoll for my model is colliding improperly with itself and causing odd collision behavior.

> A6: Redo your collision model smd in current Blender. If you used the optional method of ragdoll model creation, it's possible you made parts of the collision model overlap, which, unsurprisingly, can lead to unusual collision behavior.

Q7: The toe/foot bones on my radgoll are indented into the mesh!

> A7: This stems from a misstep in proportion trick, particularly the part involving rotation of the foot and toe bones. Time to redo proportion trick!

### >---------- VIEWMODEL ARMS ----------

Q8: My viewmodel arms look all crunchy and malformed in-game!

> A8: Make sure to use the post-proportion trick model smd when you're importing to make the arms. Using the arms in the compile template folder rather than the proportion trick compile folder will cause this mesh deformation.

Q9: My viewmodel arms are blocking part or all of my pov!

> A9: You'll need to delete some more of the c_arms mesh in Blender that's closer to where the head would be. If there are any parts that point inwards towards the head, there's a chance they'll obstruct your view.
