# Exploring Godot as a Platform for Interactive Non-Game Applications

## Introduction

A major part of our initial development research has been understanding whether a **game engine can be effectively used to develop an interactive educational and visualization application** rather than a conventional game.

Although Godot is primarily designed as a game engine, our research has shown that its capabilities extend beyond traditional game development. Godot provides a built-in UI system, 2D and 3D rendering, input handling, animation, and other real-time visualization capabilities that can also be used to develop interactive desktop applications, simulations, educational tools, and visualizers. The official Godot documentation explicitly discusses the development of non-game applications and provides examples such as **Material Maker** and **Pixelorama**.

This is particularly relevant to our Final Year Project because our objective is not to develop a conventional game. Instead, we intend to create an interactive environment for **visualizing and explaining Computer Science concepts**, potentially including areas such as memory management, computer architecture, complexity, operating systems, and other computational concepts.

## Godot for Non-Game Software

To investigate this approach further, we reviewed material from the official Godot community and development team.

One particularly relevant presentation was **“Making (Non-Game) Software With Godot”**, presented by Benjamin Oesterle at **GodotCon 2024**. The presentation demonstrates how Godot can be used as a UI framework for non-game software and discusses the development of *Habituary*, a free and open-source to-do list application created with Godot. The presentation also covers Godot's Control nodes, responsive interfaces, theming, and some of the limitations that developers may encounter when using the engine for conventional software.

We also reviewed **“Building cross-platform non-game applications with Godot”**, presented by HP van Braam at **GodotCon 2025**. This presentation is particularly significant to our project because it discusses **MSEP.one**, a complex nanotechnology design utility built using Godot. The application demonstrates that the engine can be used for specialized scientific and technical visualization software rather than only games.

The MSEP.one example is especially relevant to our concept because it demonstrates the use of an interactive visual environment to represent complex technical information. This is conceptually similar to our goal of representing abstract Computer Science concepts through interactive visualizations.

## Existing Non-Game Applications Made With Godot

Our research also identified several established applications that demonstrate Godot's usefulness outside traditional game development.

**Material Maker** is an open-source procedural material and texture authoring application built with Godot. It uses a node-based interface to create and manipulate materials and supports 2D and 3D workflows.

**Pixelorama** is another open-source application developed with Godot and is designed for pixel-art creation.

Godot's official showcase also maintains a dedicated **Apps & Tools** category containing projects such as Material Maker, Pixelorama, Xogot, RPG in a Box, and other software projects.

These examples demonstrate that using Godot does not necessarily imply that the final product must follow a conventional game structure. Instead, the engine can provide the rendering, interface, interaction, and visualization layer required by a specialized application.

## Learning Godot

As part of our implementation preparation, we have started learning Godot through a combination of **official Godot documentation and external educational resources, including YouTube courses and tutorials**.

The official documentation is being used as our primary technical reference for understanding the engine's architecture, nodes, scenes, scripting, UI system, input handling, C# integration, and other engine features. External tutorials and courses are being used to supplement the documentation with practical examples and implementation techniques.

Our approach is therefore not based on following a single tutorial from beginning to end. Instead, we are gradually learning individual Godot concepts and applying them to small prototypes related to the requirements of our own project.

## Choosing C# Instead of GDScript

We also evaluated the scripting languages available in Godot. Godot officially supports both **GDScript and C#**, among other options. GDScript is specifically designed for Godot and has a simpler syntax, making it an excellent language for beginners and rapid Godot development.

However, we decided to use **C# with the .NET version of Godot** for this project.

One of the primary reasons is that C# is a mature, general-purpose programming language with a large ecosystem and extensive .NET libraries. Godot's official documentation specifically describes C# as a mature and flexible language with a large number of available libraries. Since Godot's C# integration uses .NET, third-party .NET libraries can also be used where appropriate.

C# also provides strong support through professional development environments such as Visual Studio and Visual Studio Code, including features such as IntelliSense and other development tools. This is useful for a project that is expected to grow into a larger and more structured codebase.

Another consideration is platform support. Godot's C# projects support desktop platforms including **Windows, Linux, and macOS**, with additional mobile support available with some limitations.

Our choice of C# is therefore based primarily on the combination of:

* A mature general-purpose programming language
* The .NET ecosystem and available libraries
* Strong IDE and development-tool support
* Strong typing and structured code organization
* Desktop cross-platform support
* Compatibility with Godot's existing scene and node architecture

At the same time, we recognize that GDScript has advantages within Godot, particularly its simplicity and close integration with the engine. Our decision to use C# is therefore a project-specific development choice rather than an assertion that C# is universally superior to GDScript.

## Conclusion

Our investigation has established that Godot can be used for more than conventional game development. Official documentation, conference presentations, and existing applications demonstrate that the engine can support interactive non-game software, including technical tools, creative applications, simulations, and specialized visualization software.

This makes Godot particularly interesting for our project because our intended application relies heavily on **interactive visualization and real-time representation of abstract concepts**.

We will continue learning Godot and C# through official documentation, practical experimentation, and supplementary tutorials while developing small prototypes that gradually evolve toward the final project architecture.
# References

The following resources were consulted during our research into Godot, C# development, and the use of Godot for interactive non-game applications.

1. **Godot Engine – Official Documentation, Godot 4.7**
   Official documentation used as the primary technical reference while learning the Godot Engine, including its scene and node architecture, scripting, 2D/3D systems, and development workflow.
   [Godot 4.7 Documentation](https://docs.godotengine.org/en/4.7/?utm_source=chatgpt.com)

2. **Godot Engine – Introduction**
   Provides an overview of Godot as a free and open-source 2D and 3D engine and introduces the official learning resources and documentation structure.
   [Godot Engine Introduction](https://docs.godotengine.org/en/4.7/about/introduction.html?utm_source=chatgpt.com)

3. **Godot Engine – List of Features (Godot 4.7)**
   Consulted for information regarding supported scripting languages, C#/.NET support, supported platforms, and the capabilities of Godot 4.7.
   [Godot 4.7 Feature List](https://docs.godotengine.org/en/4.7/about/list_of_features.html?utm_source=chatgpt.com)

4. **Godot Engine – Non-Game Applications FAQ**
   Official documentation confirming that Godot can be used to develop non-game applications and discussing its built-in UI system and examples of existing applications created with Godot.
   [Godot FAQ – Non-Game Applications](https://docs.godotengine.org/en/4.6/about/faq.html?utm_source=chatgpt.com)

5. **GodotCon 2024 – “Making (Non-Game) Software With Godot” – Benjamin Oesterle**
   An official GodotCon presentation discussing the development of non-game software with Godot. The presentation uses *Habituary*, a to-do list application, as a practical example and discusses Godot's UI system, Control nodes, responsive interfaces, theming, and practical challenges.
   [Watch on YouTube – GodotCon 2024](https://www.youtube.com/watch?v=cJ5Rkk5fnGg&utm_source=chatgpt.com)

6. **GodotCon 2025 – “Building cross-platform non-game applications with Godot” – HP van Braam**
   An official GodotCon presentation focused specifically on developing cross-platform non-game applications with Godot. It discusses **MSEP.one**, a nanotechnology design utility developed using Godot, making it particularly relevant to our project's concept of using interactive visualization for technical and educational purposes.
   [Watch on YouTube – GodotCon 2025](https://www.youtube.com/watch?v=ywl5ot_rdgc&utm_source=chatgpt.com)

7. **Godot Engine – Official Showcase**
   The official showcase was consulted to examine real-world projects created with Godot, including both games and applications/tools. The Apps & Tools section demonstrates that Godot is being used beyond conventional game development.
   [Godot Engine Showcase](https://godotengine.org/showcase/?utm_source=chatgpt.com)

8. **Godot Engine – Material Maker Showcase**
   Material Maker is an open-source procedural material and texture authoring application built with Godot. It provides an example of using Godot's interface and rendering capabilities for specialized creative software rather than a conventional game.
   [Material Maker – Godot Showcase](https://godotengine.org/showcase/material-maker/?utm_source=chatgpt.com)

9. **Godot Engine – Pixelorama Showcase**
   Pixelorama is an open-source pixel-art application developed using Godot. It demonstrates another example of Godot being used to create a complete creative desktop application.
   [Pixelorama – Godot Showcase](https://godotengine.org/showcase/pixelorama/?utm_source=chatgpt.com)

10. **Godot Engine – C# Documentation**
    Official documentation consulted while learning C# development with Godot and understanding the differences between C# and GDScript within the Godot environment.
    [Godot C# Documentation](https://docs.godotengine.org/en/stable/tutorials/scripting/c_sharp/index.html?utm_source=chatgpt.com)

11. **Godot Engine – Scripting Languages**
    Documentation consulted when comparing GDScript and C# and evaluating the available scripting approaches for our project.
    [Godot Scripting Languages Documentation](https://docs.godotengine.org/en/stable/getting_started/step_by_step/scripting_languages.html?utm_source=chatgpt.com)

12. **Godot Engine – Official YouTube Channel**
    The official Godot Engine YouTube channel was also used as a supplementary learning resource for tutorials, technical presentations, conference talks, and demonstrations of Godot projects.
    [Godot Engine YouTube Channel](https://www.youtube.com/@GodotEngine?utm_source=chatgpt.com)

13. **Microsoft – C# Documentation**
    Microsoft's official C# documentation was used as a supplementary reference while learning the C# language and its features.
    [Microsoft C# Documentation](https://learn.microsoft.com/en-us/dotnet/csharp/?utm_source=chatgpt.com)

14. **Microsoft – .NET Documentation**
    Microsoft's official .NET documentation was consulted to understand the broader .NET ecosystem and the libraries and development tools available to C# applications.
    [Microsoft .NET Documentation](https://learn.microsoft.com/en-us/dotnet/?utm_source=chatgpt.com)

