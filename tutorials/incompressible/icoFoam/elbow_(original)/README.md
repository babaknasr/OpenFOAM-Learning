## Folder and Files explained:
* Folder **0** contains initial condition
    * File **P**: Pressure (important: P represents pressure/density)
    * File **U**: Velocity

* Folder **constant** contains constants and material properties

* Folder **system** contains the parameters and controllers that control the simulation settings (numerical methods,...)
    * File **controlDict**: Controls for the simulation
    * File **fvSchemes**: Specify discretization schemes
    * File **fvSolution**: Specify solvers and tolerances

## Steps to Run:
### Pre-Processing (Import the mesh)
Use command ```fluentMeshToFoam``` to convert fluent mesh file (.msh) to OpenFOAM mesh. Here the msh file is *elbow.msh*. The command will be:
```
fluentMeshToFoam elbow.msh
```

A folder (**polyMesh**) will be created in **constant** folder that contains mesh files.
* In **boundary** file, check the boundary names to be matched with those specified in **U** and **P**.

### Check the geometry and mesh:
Use ```paraview &``` command to open up ParaView and follow:
* 1 Click File->Open and select All Files(*)
* 2 Open the **controlDict** file
    * Note: **controlDict** has no extension but the format is a *.foam* file (can be renamed to a *.foam* file and be recognized by ParaView in default)
* 3 Select **OpenFOAMReader** in the **Open Data With...** window
* 4 Click on Apply to show the geometry and select **Surface With Edges** in the top drop-down menu to show the mesh
* 5 Check the geometry and boundaries using **Mesh Region** list in **Properties** (left menu)

Alternatively, we can use ```paraFoam &``` command in the main directory and it will open ParaView and load the solution automatically.

### Run
Use ```icoFoam``` command in the case main directory (here is *elbow* directory)

### Processing
For every time step there is folder contains the solution files. Here, the files are: 
* **U**  : Velocity
* **p** : Pressure/Density
* **phi** : Flux through the faces

### Post-Processing
Use ```paraview &``` or ```paraFoam &``` as before.

Another command to prepare the solution files for ParaView is ```foamToVTK``` that converts results to VTK format in a new folder named "VTK".

**Hint:** Consider ***Filters->Data Analysis*** menu in ParaView for data post-processing
