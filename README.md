# libtiled

This repository was created to serve as the [libtiled](https://github.com/bjorn/tiled/tree/master/src/libtiled) submodule for [Bacon2D](https://github.com/Bacon2D/Bacon2D).

To make **libtiled** work for **Bacon2D**, the following workarounds were performed:
- **DEFINES += TILED_LIBRARY** was added to **libtiled.pri**.
- **QMake** cannot tell the difference between two classes with the same name in two different namespaces. In the case of **Bacon2D** and **libtiled**, this would cause clashes with **Layer** and **ImageLayer**, because both classes exist in both repositories. In order to resolve that, **tiled_** was appended to the **.cpp** file names. So instead of **layer.cpp** and **imagelayer.cpp** for the **libtiled** class, it is **tiled_layer.cpp** and **tiled_imagelayer.cpp** respectively.