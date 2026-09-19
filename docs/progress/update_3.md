# FYP Implementation Strategy – Initial Technical Investigation

## 1. Project Overview

The proposed Final Year Project is an interactive application for visualizing core computing concepts through simulations.

The application may cover concepts from multiple areas of Computer Science, including:

* Data Structures and Algorithms
* Operating Systems
* Concurrency and Synchronization
* Parallel and Distributed Computing
* Other relevant computing concepts identified during the development phase

The main objective is not simply to display static diagrams or basic animations. The application is intended to provide an interactive simulation in which users can observe how computing concepts behave internally and interact with the simulation.

The visualization will primarily focus on **3D**, while simpler concepts may use **2D visualization where appropriate**.

The exact concepts and final scope are still under discussion and will be finalized after further technical investigation.

---

# 2. Initial Implementation Requirements

Based on the current project concept, the application will likely require the following major capabilities:

### Simulation

The application should contain an internal representation of the computing concept being demonstrated.

For example, an operating-system simulation could contain:

* Processes
* Threads
* CPU cores
* Queues
* Resources
* Memory
* Scheduling states

Similarly, an algorithm visualization could contain:

* Nodes
* Edges
* Arrays
* Trees
* Graphs
* Algorithm states

These objects should have states that change during the simulation.

### Visualization

The internal simulation state should be represented visually.

For example, instead of simply displaying that a process changes from `READY` to `RUNNING`, the application could visually represent the process moving between a ready queue and a CPU.

### Interaction

The user should be able to interact with the simulation rather than only watching a predefined animation.

Potential interaction features include:

* Starting and pausing simulations
* Stepping through individual operations
* Adjusting simulation speed
* Changing input values
* Inspecting objects and their states
* Manipulating simulation parameters
* Potentially creating specific scenarios such as synchronization conflicts or resource contention

These features will be evaluated further as the project scope is finalized.

---

# 3. Potential Implementation Approaches

Several implementation strategies were considered during the initial technical investigation.

## 3.1 C++ with OpenGL

One option is to build the application directly using C++ and OpenGL.

A possible technology stack could include:

* C++
* OpenGL
* GLFW or SDL
* GLM
* ImGui

This approach would provide a high degree of control over the rendering system and would provide extensive exposure to graphics programming.

### Advantages

* Full control over rendering
* Strong use of C++
* Direct interaction with the graphics pipeline
* Suitable for custom 2D and 3D visualization
* Potentially useful for exploring GPU and parallel-computing concepts

### Disadvantages

A significant amount of development would be required for infrastructure that is not directly related to the core FYP objective.

For example, the team may need to implement or integrate systems for:

* Camera management
* Rendering
* Lighting
* Materials
* Animation
* User interface
* Input handling
* Scene management
* Asset management

This could significantly increase development time and project complexity.

Therefore, OpenGL remains a technically possible option, but it may not be the most efficient approach for the current project scope.

---

# 3.2 C++ with Qt

Another possibility is developing the application as a conventional desktop application using C++ and Qt.

Qt provides extensive functionality for:

* Windows
* Menus
* Buttons
* Layouts
* User interfaces
* Input handling
* Application management
* 2D visualization

It also provides capabilities for 3D applications.

### Advantages

* Strong C++ support
* Mature desktop application framework
* Extensive UI functionality
* Suitable for conventional desktop software

### Disadvantages

The project's emphasis on interactive 3D visualization would require additional work compared with using a dedicated 3D engine.

Qt may therefore be more suitable for a primarily 2D educational visualization application than for the type of immersive 3D simulation currently being considered.

---

# 3.3 Unreal Engine with C++

Unreal Engine was also considered because it provides a complete environment for developing interactive 3D applications while supporting C++.

It provides many features that would otherwise need to be developed manually, including:

* 3D rendering
* Lighting
* Animation
* Cameras
* User interfaces
* Input handling
* Scene management
* Materials
* Audio
* Asset management

The simulation logic could still be implemented primarily in C++.

### Advantages

* Very powerful 3D capabilities
* Strong C++ support
* Extensive built-in functionality
* High-quality rendering
* Suitable for complex interactive environments

### Disadvantages

For the current project, Unreal Engine may introduce unnecessary complexity and resource requirements.

The project's primary objective is computing visualization rather than high-end graphical rendering. Therefore, using a large game engine may result in development effort being spent on capabilities that are not central to the FYP.

Unreal Engine is therefore being considered but is currently not the preferred direction.

---

# 3.4 Web-Based Application

A web-based implementation is another possible direction.

A potential technology stack could involve:

* JavaScript/TypeScript
* React
* Three.js
* WebGL or WebGPU

The application could run directly inside a web browser without requiring installation.

### Advantages

* Easy distribution
* No dedicated installation required
* Accessible through a browser
* Strong support for interactive interfaces
* Three.js and WebGL/WebGPU can provide 3D visualization

### Disadvantages

* The main implementation would move away from C++
* Systems-level simulation concepts would naturally be implemented using web technologies
* Browser limitations and compatibility would need to be considered
* Combining a C++ simulation engine with a web frontend through WebAssembly would introduce additional complexity

A web-based solution therefore remains a viable alternative, particularly if browser accessibility becomes an important project requirement.

---

# 3.5 Godot with C++

Godot is another potential implementation platform.

Godot provides built-in support for:

* 2D rendering
* 3D rendering
* Animation
* Cameras
* User interfaces
* Input handling
* Scene management
* Materials
* Audio
* Interactive application development

C++ can be used for the underlying simulation through Godot's native extension capabilities.

A possible architecture would therefore be:

```text
                Godot Application
                       |
              +--------+--------+
              |                 |
       Visualization           UI
              |
              |
        C++ Simulation
              |
       +------+------+
       |             |
      DSA           OS
       |             |
      PDC       Concurrency
```

### Advantages

* Lightweight compared with larger 3D engines
* Supports both 2D and 3D
* Suitable for interactive applications
* Provides many visualization features without requiring a custom rendering engine
* Allows the core simulation logic to be implemented in C++
* Cross-platform development
* Reduces the amount of infrastructure that the team would need to develop independently

### Current Assessment

At this stage, **Godot with C++ appears to be a promising implementation direction**, particularly because it provides the required visualization and interaction infrastructure while allowing the project to retain C++ for the core simulation logic.

However, this is **not yet a final technology decision**. Further investigation into the architecture, C++ integration, performance, UI requirements, and project scope will be carried out before the technology stack is finalized.

---

# 4. Separation of Simulation and Visualization

One of the main architectural ideas identified during the initial investigation is to keep the **simulation engine independent from the visualization layer**.

Instead of allowing the simulation logic to directly control graphical objects, the application could be structured approximately as follows:

```text
                 Simulation Core
                       |
                Simulation State
                       |
                 Events / Changes
                       |
          +------------+------------+
          |                         |
     2D Visualization         3D Visualization
          |                         |
          +------------+------------+
                       |
                    User UI
```

The simulation should contain the actual computing logic, while the renderer should determine how that state is represented visually.

For example, a CPU scheduling simulation may determine:

```text
Time 0 → Process 1 is running
Time 1 → Process 1 is running
Time 2 → Process 2 is running
Time 3 → Process 3 is running
```

The visualization system can then represent these state changes using 2D diagrams, 3D objects, animations, queues, or other visual elements.

The scheduler itself should not need to know whether a process is represented by a cube, model, icon, or another graphical object.

---

# 5. Advantages of a Renderer-Independent Simulation

Keeping these systems separate would provide several potential benefits.

### Easier development

The computing logic can be developed and tested independently from the graphical interface.

### Easier debugging

If an algorithm produces an incorrect result, it can be tested without involving the rendering system.

### Multiple visualization modes

The same simulation could potentially be represented using different visualization methods.

For example:

```text
              Same Simulation
                     |
          +----------+----------+
          |                     |
        2D View               3D View
```

### Easier expansion

Additional computing concepts could potentially be added without redesigning the entire rendering system.

### Better project structure

The project can be divided into clear components such as:

```text
Simulation
Visualization
User Interface
Input
Data/Configuration
```

This could also make development easier when different team members are working on different parts of the project.

---

# 6. Potential Interaction Model

Another important idea is to treat the application as a **simulation environment rather than a collection of animations**.

Possible controls could include:

### Play/Pause

Run or stop the simulation.

### Step

Advance the simulation by one logical operation.

### Simulation Speed

Allow the user to control the speed of the visualization.

For example:

```text
0.25x
0.5x
1x
2x
4x
```

### Inspect

The user could select an object and view its current state.

For example:

```text
PROCESS #4

State: READY
Priority: 7
Burst Time: 14 ms
CPU Time: 8 ms
Waiting Time: 6 ms
```

### Parameter Control

Users could potentially modify inputs and observe how the simulation changes.

This could make the application useful not only for demonstration but also for experimentation and learning.

---

# 7. Potential Long-Term Architecture

If the project develops into a larger collection of computing simulations, a general architecture could look like:

```text
                    APPLICATION
                         |
              +----------+----------+
              |                     |
        Simulation Manager        UI
              |
       +------+-------+----------+
       |              |          |
      DSA             OS        PDC
       |              |          |
 Algorithms      Processes    Threads
 Graphs          Memory       Synchronization
 Sorting         Scheduling   Parallelism
       |
       +------------------------+
                                |
                         Simulation State
                                |
                       Visualization Layer
                          /           \
                        2D             3D
```

The exact architecture will depend on the final scope and the concepts selected for implementation.

---

# 8. Current Direction

Based on the initial technical investigation, the current direction is:

**Potential platform:** Desktop application

**Potential engine:** Godot

**Potential core language:** C++

**Visualization:** Primarily 3D, with 2D visualization where appropriate

**Architecture:** Simulation logic separated from visualization/rendering

**Primary focus:** Interactive simulation of computing concepts rather than simple predefined animations

**Status:** Preliminary investigation; final technology stack and scope have not yet been confirmed.

The next stage of investigation will focus on designing the **simulation architecture itself**, including how simulations will represent state, events, time progression, pausing, stepping, user interaction, and communication with the visualization layer. This architecture will then be used to determine the most appropriate final technology stack.
