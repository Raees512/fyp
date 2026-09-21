## Learning About Build Systems and CMake

Today, we learned about build systems and how they are used in C++ projects. Until now, we had mostly worked with C++ through an IDE where we could write our source code and simply press the Run button without knowing much about what was happening behind the scenes.

We learned that a C++ application can consist of many source files, libraries, dependencies, and different components. The compiler is responsible for compiling the source code, while the linker combines the resulting pieces and their dependencies into an executable program. A build system helps manage this process and defines how the different parts of a project should be built and connected.

We also learned about **CMake**, which is a tool used to describe the structure and build requirements of a project. Instead of manually managing every source file, library, dependency, and compiler option, these requirements can be defined in a `CMakeLists.txt` file. CMake can then generate the appropriate build files for the development environment being used.

This is particularly useful for our FYP because our project will grow into a multi-component C++ application. We expect to have separate parts for the core simulation and algorithms, application logic, visualization, testing, and potentially additional libraries or dependencies. Using a build system from the beginning should make it easier to manage these components as the project grows.

We also learned that CMake does not replace the compiler or linker. Instead, it describes how the project should be built, while the actual compilation and linking are performed by the underlying development tools.

For our project, CMake can also support the architectural approach we are considering, where the **simulation and core logic remain independent from the visualization layer**. This will allow us to build and test the core algorithms separately and connect them to the visualization system through clearly defined interfaces.

As our next step, we plan to learn the basic CMake workflow by creating a small multi-file C++ project and then apply these concepts to our FYP while continuing to learn about software architecture and project organization.
