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
### Create (Import) the mesh
Use command ```fluentMeshToFoam``` to convert fluent mesh file (.msh) to OpenFOAM mesh. Here the msh file is *elbow.msh*. The command will be:
```
fluentMeshToFoam elbow.msh
```

A folder (**polyMesh**) will be created in **constant** folder that contains mesh files.
* In **boundary** file, check the boundary names to be matched with those specified in **U** and **P**.

### Check the geometry and mesh:
Use ```paraview &``` or ```paraFoam &``` command to open up ParaView and follow:
* 1 Click File->Open and select All Files(*)
* 2 Open the **controlDict** file
* 3 Select **OpenFOAMReader** in the **Open Data With...** window
* 4 Click on Apply to show the geometry and select **Surface With Edges** in the top drop-down menu to show the mesh
* 5 Check the geometry and boundaries using **Mesh Region** list in **Properties** (left menu)

### Run
Use ```icoFoam``` command in the case main directory (here is *elbow* directory)

### Solution
For every time step there is folder contains the solution files. Here, the files are: 
* **U**  : Velocity
* **p** : Pressure/Density
* **phi** : Flux through the faces