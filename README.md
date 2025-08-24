# CS330-Comp-Graph-and-Visualization

## About This Repository
This repo contains my final 3D scene for CS 330 and the design decisions document. The scene is a desktop still life built from low-polygon primitives with textures, lighting, and interactive camera controls.

## Artifacts Included
- 3D Scene ZIP folder with source and executable
- Design Decisions document (2 pages)
- Reflection document

## How I Approach Designing Software
I start from the reference image, list the simplest primitives for each object, and group transforms and materials per object. Responsibilities are split across `SceneManager` (draws scene), `ShapeMeshes` (mesh ownership), and `ShaderManager` (uniforms and materials). Camera and lights are planned early to keep proportions readable while modeling.

### New Design Skills From This Project
- Decomposing real objects into reusable primitives with shared transform chains
- Writing small geometry helpers for tubes and arc sections to reuse across assets
- Planning texture usage by aspect ratio and tiling to avoid stretching

### Design Process I Followed
1. Block out the layout with planes and boxes.
2. Replace blocks with cylinders, cones, and spheres.
3. Add textures where they add the most value and tune UVs.
4. Add two lights and adjust ambient, diffuse, specular.
5. Iterate on proportions and placement until the composition reads well.

### Tactics To Reuse In Future Work
- Keep a clean transformation chain per object
- Build small reusable mesh generators for repeated shapes
- Add lighting early and adjust while modeling

## How I Approach Developing Programs
I modularize the code so draw calls stay simple, with transforms and materials set through small helpers. Geometry is interleaved (position, normal, UV) for generated meshes. Textures are loaded with mipmaps and consistent sampler state.

### New Development Strategies Used
- Interleaved VBOs for generated meshes
- Texture loading with mipmaps and clamp settings
- Parameterized generators for a hollow tube and a torus section used for the mug and its handle

### Role of Iteration
Work happened in short loops: add one object, verify from multiple camera angles, adjust scale and position, then move to the next. Textures and lighting were tuned after each round to keep visual feedback accurate.

### How My Approach Evolved
Early milestones focused on single objects. The final build emphasized scene composition, reuse, and polish: consistent materials, shared geometry helpers, and precise alignment.

## How Computer Science Helps Me Reach My Goals
This project shows how to move from a reference to a functioning 3D prototype with code that is testable and reusable. The same habits apply to engines, visualization, and technical art where clarity and modularity matter.

### Educational Pathway
I can extend this work with normal mapping, shadows, PBR materials, and post processing in future courses.

### Professional Pathway
The scene demonstrates core skills used in many roles: mesh generation, transforms, materials, and lighting. The structure can support interactive demos, technical art prototypes, or visualization tools.

## Build and Run Notes
- The ZIP includes Visual Studio project files and an EXE for quick verification.
- Textures live in the `textures` folder and load at startup.

**Controls**
- W A S D and Q E for movement
- Mouse to look
- Mouse scroll to adjust movement speed
- Key toggle to switch between orthographic and perspective views

## Scene Summary
**Objects**: table and legs, monitor with stand, keyboard, mouse pad, mouse with buttons, pencil holder, full pencils with colored tips, book stack, mug with handle.  
**Shapes used**: box, plane, cylinder, cone, sphere, torus section.  
**Textures**: wood, marble, keyboard top, mouse pad.  
**Lighting**: one directional and one point light with tuned ambient, diffuse, and specular.  
**Placement**: objects are aligned and scaled to match the reference layout.
