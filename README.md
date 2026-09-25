# EDM Inspector

EDM Inspector is a Windows tool for DCS World modders. It opens, inspects, edits and exports `.edm` models, shows DCS maps in 3D, sends models to Blender and Substance Painter, manages liveries, and lets you browse the functions inside a mod's DLL.

Download: [latest release](../../releases/latest), one file named `EDM-Inspector.exe`.

## What it does

### Open and inspect EDM models
- Opens `.edm` files (format versions 10 and 11) and validates them.
- 3D viewport with wireframe, solid, material preview and rendered shading.
- Outliner listing every node in the model, with an eye toggle to show or hide each part.
- Click a part in the viewport to select it. Box select, add to selection, hide, isolate, invert.
- Properties panel with the values of the selected node.
- Textures panel showing every material and its textures, read from loose files or DCS texture zips. Open any texture in a viewer with per-channel view (R, G, B, A), size, format, mip count and file location.
- Assets panel listing every model in your DCS install and mods (over 5,000). Double-click one to open it. LOD and damage variants are grouped, and the viewport can switch between LODs.
- Clickable data: reads a cockpit's `clickabledata.lua`, lists each control with its argument and action, shows it on hover in the viewport, and selects the parts it drives.
- Collision shapes and model boxes can be drawn in the viewport.
- Arguments panel with a slider for every animation argument, including Lua argument names. Scrub them or play them to see the model animate.

### Edit
- Edit values in the Properties panel and save them back to the `.edm`. The original is backed up first.
- Move, rotate and scale parts in the viewport. Undo with Ctrl+Z.
- Replace any texture from a PNG, TGA or DDS file. The original is backed up first.
- Rename nodes and arguments for your own reference. Renames are not written to the model.
- Structural editing: add groups, transforms, animated nodes and connectors, duplicate, delete and re-parent nodes. Every index is renumbered for you, each edit is validated and can be undone.
- Livery manager: lists every livery of an aircraft, previews one on the model, and edits `description.lua`.

### Blender
- Export a model or a selection to a `.blend` file with meshes, materials, skinning and animation baked as keyframes on the objects.
- Bring edited keyframes, vertex positions, normals and UVs back from Blender into the `.edm`.
- Export any selection, or a whole map area, as an OBJ or GLB mesh with materials and textures. No Blender needed for that.

### Substance Painter
- Send a selection to Painter as a new project with one texture set per material and every texture of those materials loaded into the project's Assets.
- Import the painted textures back over the model's textures. The originals are backed up first.
- This Painter API version cannot place textures on layers automatically, so you drag them onto fill layers.

### DCS terrain maps
- Open any installed DCS terrain, or a third-party terrain you point it at.
- Shaded or coloured relief, airfields with runways, radio frequencies, callsigns, navigation aids (VOR, TACAN, ILS, NDB), towns, roads and railways.
- Search by name, frequency, callsign or TACAN channel.
- Coordinates in DCS x/z, latitude/longitude and MGRS, with a Go to box and a batch converter.
- Measure distance and true bearing, get flight time, and draw an elevation profile with line of sight.
- Export airfields, navaids and towns to CSV, GeoJSON or KML. Export roads as GeoJSON or Blender-ready OBJ lines. Export a single airfield as SVG. Export relief as a heightmap PNG, ESRI ASCII grid or OBJ mesh.
- Open a map in 3D in the main viewport: the real terrain mesh (read from the map's `.surface5` file), roads, airfields with runways, towns and navigation aids, each with an eye toggle and click-to-select.
- The real terrain mesh is an early version (sea gaps, coarsest level only). Static objects placed on the map and their models are not read yet.

### DLL Explorer
- Opens a mod DLL through Ghidra and lists its functions, classes, strings, imported libraries and exports.
- Shows what a function calls and what calls it, virtual function tables of classes, and which functions use a string.
- Makes C++ names readable and checks imported names against the DLL they come from (for example EDCORE.DLL in your DCS folder).
- Decompiles a function on demand and remembers the result.
- Flag any item and attach a status and a note. Notes are kept per DLL.
- Export a DLL, its dependencies, a Ghidra project and a ready-made prompt as one zip to hand to an AI, then import the AI's answers back next to your own notes.

### Viewport controls
- Choose which mouse button and modifier key orbits, pans, zooms and looks around, under Preferences > Settings > Controls.

### Layout
- Every tool is a dockable panel. Drag panels around, float them, and reopen closed ones from the Window menu.
- Your panel layout is saved with each model's progress and restored when you open that model again.

## Install

1. Download `EDM-Inspector.exe` from the latest release.
2. Run it. The first run asks where DCS, Blender and Ghidra are, copies itself into place and adds shortcuts. It can also download Ghidra and Java for you.
3. No .NET install is needed.

Requirements: Windows 10 or 11 (64-bit) and a graphics card that supports OpenGL 3.3. Blender is only needed for Blender export, and Substance Painter only for Send to Substance Painter. Ghidra and Java are only needed for the DLL Explorer.

## Updates

EDM Inspector checks this repository for new releases when it starts. If one is newer than your version, it shows the release notes and offers Update now, Remind me later or Skip this version. You can also check manually from Preferences > Check for Updates. The automatic check can be turned off in Preferences > Settings.

## Notes

EDM Inspector is a tool for modding DCS World and is not affiliated with Eagle Dynamics. Only the executable is published here.
