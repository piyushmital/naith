# Media Guidelines #

Google code only provides 1 gigabyte of storage - at the time of writing 20% of it has been consumed. The last commit alone was responsible for 3% of that.

From now on all media **must** be optimally compressed, this means:

  * Hit the compress option when saving .blend files. (Be warned that it doesn't remember that you have it set - you will have to switch it on every time you open a file.)

  * We are moving to egg.pz files. (Cove is now 40 meg of egg data each commit, the main problem, which this will mostly fix.) (I already have a patch to add support to save such files from Chicken directly, will now integrate it ASAP.)

  * Many of the .png files we use are of greyscale data, most notably ambient occlusion maps, but are saved as full colour images. Blender always does this - you need to remember to open them in the GIMP and change them to greyscale.

  * On the subject of ambient occlusion maps they should be generated using the 'Approximate' method, not the 'Raytrace' method. Raytracing is noisy, approximate is not - ambient occlusion maps do not have that noise and so compress orders of magnitude better, and look nicer anyway. (Alternatively increase the sample count up enough to lose the noise. Only for those with super computers really, and you gain no useful advantage over approximate.)

  * If your blender file contains any multi-resolution geometry save it with the geometry at the lowest detail level. Blender always saves the current visualisation geometry in the .blend file as well, so this actually saves disc space; for high resolution multi-resolution a **lot** of disk space.