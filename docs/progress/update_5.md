# Technology Evaluation: Godot and C#

As we continued researching the technical requirements and possible implementation approaches for our project, we evaluated several technologies for developing the visualization and simulation application. Our primary focus was on finding a solution that would provide strong 3D capabilities while remaining practical for our team to develop, maintain, and extend throughout the project.

After comparing different approaches, we are currently considering **Godot Engine with C#** as our preferred development stack.

Godot provides the core features required for our application, including 3D rendering, scene management, user interface development, input handling, animation, and interaction. This allows us to focus our development effort on the actual educational and simulation functionality instead of implementing low-level graphics and engine functionality ourselves.

Another important factor is the use of **C# with .NET**. C# is a cross-platform language supported by the .NET ecosystem, allowing applications and libraries to target multiple operating systems and architectures where the required runtime and library support is available. The .NET ecosystem also provides access to a large collection of existing libraries and development tools, which can reduce the need to implement commonly required functionality from scratch.

Initially, we considered using **C++ with Godot through GDExtension**. This approach remains technically viable and would provide a native C++ layer for implementing our algorithms and simulation systems. However, it also introduces additional configuration and integration requirements, including the `godot-cpp` bindings, native library compilation, and maintaining the C++/Godot integration.

At this stage, we believe that using C# can provide a cleaner development workflow while still allowing us to implement the core computational components of the project ourselves. The project will still involve substantial programming in areas such as:

* Data structures and algorithms
* Algorithm simulation and step-by-step execution
* Graph and other computational models
* Simulation state management
* Event and interaction systems
* 3D visualization
* User interface and controls
* AI-assisted educational functionality
* Testing and evaluation

Therefore, the decision to use C# is not intended to reduce the technical depth of the project, but rather to reduce unnecessary integration overhead and allow us to focus our effort on the actual objectives of the application.

Our current proposed separation of responsibilities is:

```text
                    Godot Engine
                 3D / UI / Interaction
                         │
                         ▼
                  C# Application Layer
                         │
             ┌───────────┴───────────┐
             │                       │
      Simulation Core            AI Service
             │
      ┌──────┼────────┐
      │      │        │
    Graph  Data     Algorithms
           Structures
```

This architecture is still under evaluation and may evolve as we build prototypes and identify practical requirements. Rather than committing to the complete architecture immediately, our next step is to create small prototypes and evaluate the workflow before finalizing the technology stack.

The main objective at this stage is to make a technically sound decision based on actual implementation experience rather than choosing a technology solely because it is familiar or theoretically more powerful.
