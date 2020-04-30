# ModelLoader
Simple Model Viewer made with C++

### Project Specification
The goal for this project is the creation of an openGL model loader using C++. The application can be run from command line, read .obj and .mtl files and display them in an openGL window.

### Program Versions
* Visual Studio 2017
* OpenGL 4.0
* glm v0.9.9.600
* NupenGL.Core v0.1.0.1
* NupenGL.Core.Redist v0.1.0.1
* AntTweakBar 1.16

### How to use
##### Setup
The project can be opened by opening 'ModelLoader.sln' in Visual Studio.
A folder named 'media' should be in the same directory as the project/executable. This folder should contain the .obj file, the .mtl file, and any relevant image files required to load models. Any .mtl files should be renamed to have the same name as their .obj file.

##### Using the application
On startup, the application will create an empty openGL window holding a GUI. This is displayed below:

![Startup Screen](/Documents/image/startUp.JPG)

To load a model into the window, press the button marked "Load First Model" in the first section of the GUI.

![Console Input Window](/Documents/image/consoleInput.JPG)

This will prompt the input of the filename of the .obj file to load, without the file extension. Inputting a valid file path will load the selected model into the openGL window. The position, scale, and rotation speed of this object can be changed using the options under the "First Model Loading" header of the GUI.

A second model can be loaded and interacted with using the options under the header "Second Model Loading". This can only be done if a model has already been loaded using the "Load First Model" option

When viewing a model, the camera can be moved using the GUI option, or via the W/A/S/D/Q/E keys. 
The application can be closed by either pressing the "Close Application" button in the GUI, or by pressing the ESC key.

### Program Structure
The program contains the following methods:
* Main: Holds the loop for displaying materials, and starts the initialisation of model data
* Display: Creates camera view matrix and draws the contents of each VAO
* GetUserInput: Handles keyboard presses from the user while in the display loop
* Init: Populates VAO to load the first model
* InitSecondModel: Populates second VAO to load a second model
* OBJParser: Reads an obj file from a given path
* GetPath: Used to generate a correct file path from user input
* CheckFileExists: Returns if a given file path points to an existing file
* MTLParser: Reads a .mtl file from a given path
* GUISetup: Creates a GUI on startup
* TWCallEvents: Contains event definitions for use with the GUI

The class 'Material' is used to store the data read in by the material parser
