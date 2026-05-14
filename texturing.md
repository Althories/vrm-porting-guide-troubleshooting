## This file contains troubleshooting fixes for texturing issues. A lot of texure bugs are simply typos or mistakes in the main .qc or the .vmt files, so be sure to pay attention!

Q: I've set up my .vmt files to display textures in-game, but my model still appears untextured!

> A: Before checking anything, switch to the 'View' tab in Crowbar after compiling the model. If the 'Material File Names' section only shows one material called 'Material', the textures will not display. You may need to downgrade the current newest version of Blender and re-export from there for the materials to process correctly. You can verify the materials present by checking the compile log of a model in this View tab. If the list here mismatches your list of materials in Blender, you will need to make some changes.

> A: The most common reason this occurs is because a directory is pointing to the wrong place. Ensure that your $cdmaterials line in the main .qc compile file is pointing to the right place. This can also occur within your .vmt files, so ensure your directory names are correct.

> A: Make sure the materials are actually in the addons folder inside the Gmod directory.

> A: If some but not all of your textures are displaying, your directories are correct in only some of your .vmt files.

Q: I've set up my .vmt files to display textures in-game, but my model appears as a white wireframe outline!

> A: You're missing "VertexlitGeneric" at the top of your .vmt files, or it is misspelt.

Q: My model is textured, but there's a purple tint over it!

> A: You're missing base.vtf in your materials/models/yourmodel_pm folder. Or, you have base.vtf and there's a typo (or typos) in a file (or files) referencing base.vtf. Check your .vmt files to make sure your lines are correct!

Q: My model is correctly textured, but the square icon for my model in the playermodel selector is untextured.

> A: This is a clientside issue. Navigate to GarrysMod > garrysmod > materials > spawnicons > models. You can pick out your username from the list of folders and enter it to delete the icon(s) (the same username used in your .qc file.) New icons will automatically be generated upon re-entering Garry's Mod, which will be textured as long as your model is textured.

Q: Some of the textures for my Vroid Studio model are combined into a single image!

> A: When you get to editing the .vmt files, all you need to do is use the texture image that contains the texture for the .vmt file you're curently editing. This means that multiple or all of your .vmt files will be directed to the same image(s). Garry's Mod should be able to figure out what part of the image it should use for each .vmt file.

