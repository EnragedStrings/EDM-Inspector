# EDM Inspector

EDM Inspector is a Windows tool for DCS World modders. It opens, inspects, edits and exports `.edm` models, explores DCS terrain maps, and lets you browse the functions inside a mod's DLL.

Download: [latest release](../../releases/latest), one file named `EDM-Inspector.exe`.

## What it does

### Open and inspect EDM models
- Opens `.edm` files (format versions 10 and 11) and validates them.
- 3D viewport with wireframe, solid, material preview and rendered shading.
- Outliner listing every node in the model, with an eye toggle to show or hide each part.
- Click a part in the viewport to select it. Box select, add to selection, hide, isolate, invert.
- Properties panel with the values of the selected node.
- Textures panel showing every material and its textures, read from loose files or DCS texture zips.
- Arguments panel with a slider for every animation argument, including Lua argument names. Scrub them or play them to see the model animate.

### Edit
- Edit values in the Properties panel and save them back to the `.edm`. The original is backed up first.
- Move, rotate and scale parts in the viewport. Undo with Ctrl+Z.
- Replace any texture from a PNG, TGA or DDS file. The original is backed up first.
- Rename nodes and arguments for your own reference. Renames are not written to the model.

### Blender
- Export a model or a selection to a `.blend` file with meshes, materials, armatures, skinning and baked animation.
- Bring edited keyframes back from Blender into the `.edm`.

### DCS terrain maps
- Open any installed DCS terrain, or a third-party terrain you point it at.
- Shaded or coloured relief, airfields with runways, radio frequencies, callsigns, navigation aids (VOR, TACAN, ILS, NDB), towns, roads and railways.
- Search by name, frequency, callsign or TACAN channel.
- Coordinates in DCS x/z, latitude/longitude and MGRS, with a Go to box and a batch converter.
- Measure distance and true bearing, get flight time, and draw an elevation profile with line of sight.
- Export airfields, navaids and towns to CSV, GeoJSON or KML. Export roads as GeoJSON or Blender-ready OBJ lines. Export a single airfield as SVG. Export relief as a heightmap PNG, ESRI ASCII grid or OBJ mesh.
- The relief is a coarse 512 m height map. The terrain's full mesh, static objects and models are not read yet.

### DLL Explorer
- Opens a mod DLL through Ghidra and lists its functions, classes, strings and imported libraries.
- Decompiles a function on demand and remembers the result.
- Flag any item and attach a status and a note. Notes are kept per DLL.
- Export a DLL, its dependencies, a Ghidra project and a ready-made prompt as one zip to hand to an AI, then import the AI's answers back next to your own notes.

### Layout
- Every tool is a dockable panel. Drag panels around, float them, and reopen closed ones from the Window menu.
- Your panel layout is saved with each model's progress and restored when you open that model again.

## Install

1. Download `EDM-Inspector.exe` from the latest release.
2. Run it. The first run asks where DCS, Blender and Ghidra are, copies itself into place and adds shortcuts. It can also download Ghidra and Java for you.
3. No .NET install is needed.

Requirements: Windows 10 or 11 (64-bit) and a graphics card that supports OpenGL 3.3. Blender is only needed for Blender export. Ghidra and Java are only needed for the DLL Explorer.

## Updates

EDM Inspector checks this repository for new releases when it starts. If one is newer than your version, it shows the release notes and offers Update now, Remind me later or Skip this version. You can also check manually from Preferences > Check for Updates. The automatic check can be turned off in Preferences > Settings.

## Notes

EDM Inspector is a tool for modding DCS World and is not affiliated with Eagle Dynamics. Only the executable is published here.
