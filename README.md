# How to Archive your Computer!

Tutorial on how to archive your own computer to be part of computers.json :-)

Everything is completely free and can be DIYed! It is okay if it it jank! It is made by humans! Lets use what we have accessible to us--no fancy, expensive equipment required! :-)

## Tools/Software needed

- Polycam (Free version, OK!)
- Your phone!
- Flatbed Photo Scanner (Find one at your local library/makerspace!)
- Blender (Free!)
- MeshLab (Free!)

## Tips

- Have a GOOD file system!
- Make sure to LABEL properly!

File Set up Example:

```
--- {name}_computer_archive (folder)
        |
        --- polycam_EXPORT (folder)
            |
            --- textures (folder)
            --- {name}.mtl
            --- {name}.obj
        --- meshlab_EXPORT (folder)
            |
            --- {name}_computer_fixedmesh.mlp
            --- {name}_computer_fixedmesh.obj
        --- flatbedScans_EXPORT (folder)
            |
            --- {name}_desktopScreenshot.png
            --- {name}_keyboardSurface_Scan.jpeg
            --- {name}_topSurface_Scan.jpeg
            --- {name}_bottomSurface_Scan.jpeg
        --- blender_file (folder)
            |
            --- {name}_computer_fixedmesh.obj
            --- {name}_computer.blend
            --- textures_UPDATED (folder)
                |
                --- (COPY flatbedScans_Export folder) HERE)
            --- textures_POLYCAM (folder)
```

## Step 1: Open Polycam

- Place your laptop on a flat surface. Ideally with good lighting.
- Take out polycam on mobile and use either auto/manual mode to take pictures of your devices (via photogrammetry). I recommend to check out this video made by Polycam for further help :)

- These are the settings to choose after:

<img src="imgs/polycam_options.jpg" alt="Polycam settings" width="300">

- I highly recommend to crop + do small edits in the polycam settings !

<img src="imgs/polycam_cleanup.png" alt="Polycam cleanup details" width="300">

- Export your model as a OBJ file !

## Step 2: Scan the Surfaces (via flatbed scanner)

*why? we want to get high quality scans because photogrammetry will not capture these fine, tiny details. Using a flatbed scanner to capture the surfaces will allow us to create high-resolution 3D 'captures'.*

Settings (I used, may differ between scanners!):
- 600 DPI (300 DPI minimum)
- JPEG OUTPUT (tiff/png is OK! no pdf)
- Scanned at Tabloid size (landscape) 

Surfaces to Scan:
- Top Surface of Laptop
- Bottom Surface of Laptop
- Inside of Laptop (keyboard & screen) *(If possible)*

<img src="imgs/flatbed_scanner.jpeg" alt="Polycam cleanup details" width="300">

You can honestly lay your laptop flat (CLOSED). And scan both sides. If your laptop can be layed flat (when its open), I would scan the inside of the laptop (keyboard + screen). When the screen is on, it wont show up but we are just capturing the other details so its ok.

<img src="imgs/top_scan.jpeg" alt="Polycam cleanup details" width="300">


## Step 2: Import 3D model -> Meshlab

*why? to ensure the mesh is optimized + fixed! we want our obj file to be as small as possible but still retaining as much detail. So we use these tools to clean up any unnecessary vertices/planes that won't effect the overall final model*

- Open your model(obj) in Meshlab to clean up vertices/planes/holes
- Every model is different but I recommend to go through filters -> cleaning & repairing folder

<img src="imgs/meshlab_settings.png" alt="Polycam cleanup details" width="300">

- Save your model(obj)

## Step 3: Import new 3D model -> Blender

**Step 3.1**

- Import OBJ file -> set origin to "Origin to center of Mass(Volume) -> scale size -> fix rotation so the model sits flat on the plane

<img src="imgs/blender_step1.png" alt="Polycam cleanup details" width="300">

**Step 3.2 - Fixing Model in Blender(Double-Checking)**

*why? usually I like to double check + fix any remaining issues in the model to ensure optimization!*

- Go into Edit mode -> Select Mode: FACE

<img src="imgs/blender_editMode.png" alt="Polycam cleanup details" width="300">


- Select All(A) -> Under "Mesh" -> "Clean Up"
    These are the clean up options I would use:
    - Fill Holes
    - Merge by Distance
    - Delete Loose

**Step 3.3 - Adding Texture to Specific Surfaces**

*why? we can align the flatbed scans onto the 3D model!*

- Make sure the "Selected: Mode" is on faces
- 
