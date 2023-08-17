- `mkdir build`
- `cd build`
- `cmake ..` OR `cmake -G "Visual Studio 17 2022" ..` - This is the command-line tool for the CMake build system; Navigate to the root directory of your project (where the main CMakeLists.txt file is).
  
What Happens When You Run cmake: \
CMake reads the CMakeLists.txt files and processes its commands.
CMake generates the necessary build files for your platform or specified build system. By default, it tries to generate build files for the most appropriate build system available on your machine (like Makefiles on Unix-like systems or Visual Studio solutions on Windows).
All the build-related files are generated in the current directory (build in this example). This includes object files, libraries, executables, and any other intermediate files created during the build process.
Running cmake .. is just the configuration step. After this, you would usually invoke the build system (e.g., make, ninja, or opening the solution in Visual Studio) to actually compile and link your project.

- `cmake --build . --config Release` -  is a command-line way to build a project that has been previously configured by CMake. \
  
This is a platform-agnostic way to tell CMake to build the project. Rather than having to use make, ninja, or calling the Visual Studio build tools directly, you can use this command to build the project, and CMake will invoke the appropriate toolchain for you. This makes scripts more portable because you don't have to know in advance which build system will be used.
