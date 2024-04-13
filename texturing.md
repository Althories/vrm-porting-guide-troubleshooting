## This file contains troubleshooting fixes for texturing issues. A lot of texure bugs are simply typos or mistakes in the main .qc or the .vmt files, so be sure to pay attention!

Q1: I've set up my .vmt files to display textures in-game, but my model still appears untextured!

> A1: The most common reason this occurs is because a directory is pointing to the wrong place. Ensure that your $cdmaterials line in the main .qc compile file is pointing to the right place. This can also occur within your .vmt files, so ensure your directory names are correct. If some but not all of your textures are displaying, your directories are correct in only some of your .vmt files. Note that if you move any files or folders in your pc's filesystem, you'll have to change where the directories are pointing to, as well.

Q2: My model is correctly textured, but the square icon for my model in the playermodel selector is untextured.

> A2: This is a clientside issue. Navigate to GarrysMod > garrysmod > materials > spawnicons > models. You can pick out your username from the list of folders and enter it to delete the icon(s) (the same username used in your .qc file.) New icons will automatically be generated upon re-entering Garry's Mod, which will be textured as long as your model is textured.