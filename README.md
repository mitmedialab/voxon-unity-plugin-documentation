# voxon-unity-plugin-documentation
Documentation on the Voxon volumetric display is a little sparse, and a little scattered.  Thus, this is a repository of what we know about how it works.

Links to official documentation:

https://voxon.co/unity-plugin-update-opens-floodgates-for-vx1-content-creation/

Also see the attached PDF copy of the release notes.
The ReadMe file for the latest release includes an address for joining the slack, but the community seems sluggish to actually accept new requests to join.


Additional Tips:

The voxon will occasionally display a solid block of purple, awkwardly distort all of its images, or otherwise fail.  If shift+esc to leave voxieos does not solve the problem, restarting generally does.  

Files related to the leap motion can throw errors which prevent you from doing anything else.  Deleting them won’t damage your ability to use the non-leap-related parts of the software.

Objects in the scene will only appear if they have a collider.  The collider does not need to match the mesh of the object.  Any object can be displayed with any collider attached, but all objects need a collider.

It looks like the voxon is unable to display textures, but it fine with simpler materials.  

Your root folder should contain the following:

>Assets folder

>Library folder

>Project Settings

>Temp

>projectName_Data

>Unity Package Manager

>projectName.exe

>UnityPlayer.dll

>Voxiebox.ini

>voxiebox_menu0.ini

I have not gotten a project to work whose root folder is not structured exactly like this.

If, upon running your unity file on the voxon, you are prompted to use either display 1 or display 2, you want display 2.


The included example file should display an animated fish, which swims across the display. 
