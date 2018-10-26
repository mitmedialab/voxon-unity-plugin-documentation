Setting things up

The SDK can be downloaded here.  Drag the VoxonUnity folder into the Assets folder of your project, and it will handle the rest of the work of setting itself up.  

Where is the official documentation?

There’s this 3-minute YouTube video.
There’s also a helpful word document in the SDK itself.  Check VoxonUnity>docs>UtilizingVoxonUnityPluginGuide.

Keyboard input

One would assume that, because there’s a Unity SDK for the Voxon, you would be able to just write standard Unity code to detect things like keyboard and mouse input:

	void Update(){
		if (Input.GetKey("a")) {
			Debug.Log(“You pressed the A key!”);
		}
	}

This is not how detecting Keyboard input works at all.  Instead, take a look at the Input Controller script on the capture volume.  



Default.json is the name that key bindings are saved to.  You can change that to a different file name, in order to store different sets of key binding under different names. The names on the left side are what you will call with other code.  The values that you grab from that very large drop-down menu on the right side are the actual input methods.  

IMPORTANT NOTE: YOU MUST HAVE A KEY BINDING FOR QUIT.  OTHERWISE NOTHING WILL RUN.

ANOTHER IMPORTANT NOTE:  YOU HAVE TO SAVE AND RELOAD THE KEYBINDINGS JSON FILE EVERY TIME YOU CHANGE YOUR KEY BINDINGS, BEFORE GOING INTO PLAYMODE. 

Then, instead of using the code listed above, you would say something like this:

		if (Voxon.Input.GetKey ("Debug")) {
			Debug.Log(“You pressed the A key!”);
		}

	Where “Debug” is mapped to A.


This can then be extrapolated to write all other key bindings.  If you’ve done work with a web framework with url bindings, this kind of logic makes some sense, but it’s still not the most intuitive thing in the world.

BUT. It still doesn’t work.  Please keep in mind that this was built by a team of 8 guys in Australia.  

There’s a framework file in the example project called KeyboardInput.cs.  It has a lot of boilerplate which can’t easily be changed.  That code is all marked with “//keep this” comments.  Everything else aside from this can be changed.  The example code which isn’t marked as “//keep this” should give you a basic tool kit of things that you can control about your scene.  All keyboard input needs to be written in this file.  



Exporting

The video linked above does a good job of describing how to export your project, but if you find yourself doing a lot of pausing and squinting, here’s a quick summary.

File>Build (not Build & Run!) 

If there are no scenes in the “scenes in build” box, click “Add Open Scenes”

Then just hit build

Then, go into Assets>VoxonUnity>default_settings and grab the voxiebox.ini and voxiebox-menu.ini files, and move them up into the root folder (should be up at the same level as the Assets folder, and your new exe file.  They are sometimes already there, and sometimes not.  The Voxon is a mysterious creature.

Then, go drop your whole file onto the Voxon via a flashdrive (it is unconnected from the internet so that it does not update and destroy itself), and find it via voxieos.


Other Tips and Tricks

Objects in the scene will only appear if they have a collider. The collider does not need to match the mesh of the object. Any object can be displayed with any collider attached, but all objects need a collider.


If, upon running your unity file on the voxon, you are prompted to use either display 1 or display 2, you want display 2.


