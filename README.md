# OpenGL planet cubes with texture and a some lighting

This is a university project. Please check out [https://learnopengl.com](https://learnopengl.com) for complete turtorial
of OpenGl. 99% of the code in the repo is written by [Joey de Vries](http://joeydevries.com/) and you can find it
here [Github](https://github.com/JoeyDeVries/LearnOpenGL)

## Windows building

All relevant libraries are found in /libs and all DLLs found in /dlls (pre-)compiled for Windows.
The CMake script knows where to find the libraries so just run CMake script and generate project of choice.
Note that you still have to manually copy the required .DLL files from the /dlls folder to your binary folder for the binaries to run.

Keep in mind the supplied libraries were generated with a specific compiler version which may or may not work on your system (generating a large batch of link errors). In that case it's advised to build the libraries yourself from the source.

## Linux building

First make sure you have CMake, Git, and GCC by typing as root (sudo) `apt-get install g++ cmake git` and then get the required packages:
Using root (sudo) and type `apt-get install libsoil-dev libglm-dev libassimp-dev libglew-dev libglfw3-dev libxinerama-dev libxcursor-dev libxi-dev` .
Next, run CMake (preferably CMake-gui). The source directory is LearnOpenGL and specify the build directory as LearnOpenGL/build. Creating the build directory within LearnOpenGL is important for linking to the resource files (it also will be ignored by Git). Hit configure and specify your compiler files (Unix Makefiles are recommended), resolve any missing directories or libraries, and then hit generate. Navigate to the build directory (`cd LearnOpenGL/build`) and type `make` in the terminal. This should generate the executables in the respective chapter folders.

Note that CodeBlocks or other IDEs may have issues running the programs due to problems finding the shader and resource files, however it should still be able to generate the exectuables. To work around this problem it is possible to set an environment variable to tell the tutorials where the resource files can be found. The environment variable is named LOGL_ROOT_PATH and may be set to the path to the root of the LearnOpenGL directory tree. For example:

    `export LOGL_ROOT_PATH=/home/user/tutorials/LearnOpenGL`

Running `ls $LOGL_ROOT_PATH` should list, among other things, this README file and the resources direcory.

### Linux building in Docker

Using [this project](https://github.com/01e9/docker-ide) you can start IDE in docker:

```
.../docker-ide/ide cpp-gpu ~/.../clion/bin/clion.sh -x11docker "--gpu"
```

## Mac OS X building

Building on Mac OS X is fairly simple (thanks [@hyperknot](https://github.com/hyperknot)):

```
brew install cmake assimp glm glfw
mkdir build
cd build
cmake ../.
make -j8
```

## Glitter

Polytonic created a project called [Glitter](https://github.com/Polytonic/Glitter) that is a dead-simple boilerplate for OpenGL.
Everything you need to run a single LearnOpenGL Project (including all libraries) and just that; nothing more.
Perfect if you want to follow along with the chapters, without the hassle of having to manually compile and link all third party libraries!
