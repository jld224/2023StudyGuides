# Interactive Game Design (Dr. Xiao, Spring 2023)
Adapted from https://quizlet.com/in/795280938/interactive-game-design-final-study-guide-flash-cards/ using https://platform.openai.com/playground

### What is a video game?
#### An interactive animation

### What are the 4 parts of video game interaction?
#### Data, algorithms, input, output

### What is data in regard to video games?
#### Game Objects

### What are algorithms in video games?
#### Animation

### What is input in video games?
#### Interactive Events

### What is output in video games?
#### Display

### What two parts are game objects composed of?
#### Geometry + Attribute

### What are some primitives of in-game geometry?
#### Points, lines, triangles, polygons, spheres, tetrahedrons, etc.

### What are some meshes in-game geometry?
#### Grids: elevation, uniform, rectilinear, structured, tin: a triangular integrated network

### Meshes in-game geometry are
#### Indexed

### What are some analytical elements of in-game geometry?
#### Planes, curves, surfaces, parametrical lines, curves.

### What are stroked, primitives
#### Stroked primitives paint all points covered by a line drawn over the outlines.

### What are composite game objects?
#### Composite game objects are game entities that are composed of multiple smaller game objects or components. They are often used in game development to create complex game entities that can be easily managed and modified. (Avatars, prefabs, packages)

### What are elevation grids?
#### Elevation Grids: An elevation grid is a type of grid that is used to represent terrain or elevation data. It consists of a set of regularly spaced data points, each with a corresponding elevation value. Elevation grids are often used in geographical information systems (GIS), virtual reality, and video games to create realistic representations of landscapes and terrain.

### What are uniform grids?
#### Uniform Grids: A uniform grid is a simple type of grid that consists of a set of regularly spaced data points with uniform spacing between them. It is often used in numerical simulations, where it provides a regular sampling of the simulation domain. Uniform grids are also used in computer graphics to represent 3D objects, where they provide a simple and efficient way to divide an object into a grid of smaller components.

### What are rectilinear grids?
#### Rectilinear Grids: A rectilinear grid is a type of grid that has a regular structure in two or three dimensions, where the spacing between the grid points is not necessarily uniform. In a rectilinear grid, the spacing between the grid points can vary in each dimension, allowing for a more flexible and precise representation of data. Rectilinear grids are often used in scientific visualization to represent scalar and vector data in a 2D or 3D space.

### What are structured grids?
#### Structured Grids: A structured grid is a type of grid that has a regular structure in all dimensions, where the spacing between the grid points is uniform. Structured grids are often used in numerical simulations, where they provide a regular sampling of the simulation domain and make it possible to apply numerical methods such as finite difference or finite volume methods. Structured grids are also used in computer graphics and scientific visualization to represent 3D data sets with regular structure.

### What are the characteristics of Game Object DS
#### Discrete🡺Interpolation, P1, P2, Regular/Irregular, Data Dimensions\

### What is the design criterion for game objects?
#### Compact (save space), Efficient (fast retrieval), Map-able (easy to convert), Minimal Coverage (small footprints), Simple (easy to use)

### What are the two dataset parts for a Game Object?
#### Structure, Attributes

### What composes structure in a game object dataset?
#### Topology and geometry. Topology is the set of properties invariant under certain geometric transformations. Geometry is the instantiation of the topology; the specification of positions in a 3D space.

### What composes structure in a game object attribute?
#### Color, Normal (shading), Texture coordinates (texture mapping), Material properties (strength, temperature, ...)

### What are the three faces of designing game object appearance?
#### The Artistic Face (Aesthetic - beautiful and ugly, done by artists), The Communication Face (Show and tell (convey a message), done by communication experts), The Technical Face (The enabler (can or can't), game engine design and development, done by computer scientists).

### What are the 4 attributes of Game Object appearance?
#### Color, Shading, Texture, Transparency

### What are keyframes?
#### Keyframes are the important frames that contain information on a start/end point of an action.

### What is procedural animation?
#### Animation that is created in real-time to allow more options for gameplay

### What is animation?
#### Any change that has a visual effect?

### What are motion dynamics?
#### Movements (geometry change)

### What are update dynamics?
#### Attribute changes (color, texture, etc.)

### What are the steps of Key-frame animation?
#### Defining key-frames, Inbetweening with interpolations, Lerping (linear interpolation), Parabola interpolation

### What are the equations for a parametric form of a line?

`x(t) = x0 + t * (x1 - x0) 
y(t) = y0 + t * (y1 - y0) 
0 <= t <= 1 
`
& 
`
x(t) = (1-t) * x0 + t * x1 
y(t) = (1-t) * y0 + t * y1 
0 <= t <= 1`

### What is event-driven programming?
#### The application awaits in an idle state and responds to user requests by calling the corresponding event handlers.

### What are the 5 key components of event-driven programming?
1. Events - Actions or occurrences, such as user input or system notifications, that are detected and processed by software systems.
2. Event loop - A programming construct that continuously checks for new events and processes them accordingly in a non-blocking manner.
3. Event mapping - The process of associating specific events with the appropriate software components or functions that will handle them.
4. Event dispatching - Sending an event to its designated event handler or processing function for further action.
5. Event handlers - Software components or functions that are responsible for processing specific events and carrying out the appropriate actions in response to them.

### Geometric Transformations

* Rigid-body transformations (T and R) change the location and orientation of an object, but not its size or the angle between its elements.
* Affine transformations (S and SH) can change the size, location, and angle of an object, but not its line parallelism.
* Uniform scaling is a transformation that changes the size of an object, but not its angle.
* The transformations S, R, and SH used so far are centered around the origin.

### Procedural Morphing

Procedural morphing is a technique used in computer graphics to create smooth transitions between two or more objects by generating a series of intermediate shapes using mathematical functions or algorithms.

### Time-dependent Carpet Plots Formula

y(r,t) = A e-r-at cos(2π (r-Vt) /λ);

r = sqrt ((x-x0)*(x-x0)+ (z-z0)*(z-z0))

P0(x0, y0, z0) : center of the wave

A: amplitude of the wave

V: velocity of the wave

λ: wave length of the wave

a: speed of decaying

t = current time - time of impact (t0)

### Boids/Flocking Rules

1. Separation: Boids try to maintain a minimum distance between themselves and their neighbors to avoid collisions and maintain personal space.
2. Alignment: Boids try to align their velocity and direction with their neighbors, creating a sense of coherence and group motion.
3. Cohesion: Boids try to move towards the center of mass of their neighbors, creating a sense of attraction and social organization.

### Monte Carlo Tree Search

1. Selection: Choose a node to explore based on a combination of factors such as the likelihood of winning and the number of times it has been visited.
2. Expansion: Add one or more child nodes to the selected node representing possible moves.
3. Simulation: Perform a simulation from the selected node until the end of the game or a predetermined number of moves is reached.
4. Backpropagation: Update the statistics of the nodes in the tree based on the outcome of the simulation and propagate the results up the tree to the root node.

### AlphaGo Algorithms

1. Monte Carlo tree search to search for the best move by building a tree of possible moves and their outcomes, and selecting the most promising paths through the tree based on random simulations.
2. Deep neural networks evaluate the strength of potential moves and predict the winner of the game. The neural networks are trained on a large dataset of expert Go games, allowing AlphaGo to learn from human expertise and improve its performance over time.
3. Policy networks guide their search for the best move by predicting the probability of each possible move being the best move, allowing AlphaGo to focus its search on the most promising options.
4. Value networks evaluate the strength of potential moves and predict the winner of the game by estimating the probability of each player winning the game from any given position, allowing AlphaGo to choose moves that are more likely to lead to a victory.

### Principles for Game Development

1. Pre-production - Design phase
2. Production - Main stage of development
3. Milestones - Major events of alpha, beta, and release
4. Post-production - Sales and support

### Pre-Production Stages

1. High concept - Main idea, pitch document
2. Concept documentation - Game proposal, game plan
3. Proof of concept - Prototyping, design document

### Production Aspects

1. Design - presentation and rules of the game: collaborative
2. Assets - sprites, 3D models, audio: artists
3. Code - in graphical, scripting, or major programming languages: programmers
4. Level creation - design and add features at different levels: artists and designer
5. Testing - quality assurance: testers

### Milestones

1. First playable - With limited features
2. Alpha - With full features, internal test
3. Code freeze - No more programming
4. Beta - Completed, external test.
5. Gold master - Final build for the distribution production

### Post-Production

1. Marketing - Trade shows, app stores, communities
2. Maintenance - 1:1000 rule
3. Indie Development - Independent games (indie games): Internet distribution (app stores)

### Data Structures for Game Objects

1. Voxel - volume element, the smallest element of a volume.
2. Geometry - hexagon, tetrahedron, etc.
3. Attributes
    - single-valued - one value for each voxel
    - multi-values - one value for each corner of the voxel

### Voxelization

1. Game object voxelization: In this approach, individual game objects are voxelized, which involves converting their geometry into a voxel representation. This allows for more precise collision detection and physics simulation, as well as enabling special effects and other visual enhancements.
2. Game space voxelization: In this approach, the entire game space is voxelized, which involves dividing the game world into a 3D grid of voxels. This allows for more efficient rendering and physics simulation, as well as providing a more flexible environment for procedural content generation and other gameplay features.

### Triangulation

Connect points to form a triangulated topological structure. (topology generation)

### Delaunay Triangulation (Edge Swapping)

1. Find the minimum bounding triangle. (may need to add a fake point)
2. Add one point at a time, do triangulation.
3. After each point is added, check if the joined triangles are optimal or not; if not swap the joining edge (edge swapping). Check all other triangles and make sure they are still optimal after adding the current point.
4. Repeat step 3 to add each point and we when all points are added and all triangles are optimal.
5. Clean up: remove all fake points and related triangles.

### Properties of Delaunay Triangulation

1. Circumsphic property: no other points in the circumspheres.
2. Optimal property: The minimum interior angle of a triangle is greater than or equal to the minimum interior angle of any other triangulation
3. It is the dual of the Dirichlet tessellation

### Optimal Triangulation

a triangulation that generates maximized minimum angles.

### Traversing a Gaming Space

1. Follow predefined paths
2. Follow pre-partitioned spaces
3.Follow the line of sights
4. Collision detection

### Line of Sight 
- Eyes - image generation  
- Lights - Shadow  
- Objects - collision   

### Simple Ray Tracing

```
for (each scan line in image ) {
    for (each pixel in the scan line ) {
        determine ray from eye through pixel;
        for(each object in scene) {
            if(object is intersected and is the closest considered thus far)
            record intersection point and object id. 
        }
        set pixel's color to that at closest object intersection point (using the REGULAR I formula.)
    }
}
```

### I Formula
Set pixel's color to that at closest object intersection point using the I formula given below.  

Iλ= (1- kr - kt )Iλregular+ kr Irλ+ kt Itλ  

- Iλregular: regular reflection of lights from light source. Computed by the formula above.  
- kr : reflection coefficient.  
- Irλ: illumination from other objects (to be reflected).  
- kt : transmission coefficient.  
- Itλ: illumination from other objects (to be transmitted).  

### Recursive Ray Tracing

```
for (each scan line in image ) {
    for (each pixel in the scan line ) {
        determine ray from eye through pixel;
        for(each object in scene) {
            if(object is intersected and is the closest considered thus far)
            record intersection point and object id. 
        }
        set pixel's color to that at closest object intersection point (using the RECURSIVE I formula.)
    }
}
```

### Simple Ray Tracing for Shadowing

```
for (each scan line in image ) {
    for (each pixel in the scan line ) {
        determine ray from the light through pixel;
        for(each object in scene)
            if(object is intersected)
            flag the pixel as in a shadow
    }
}

// Usually use a separate buffer (shadow buffer) of the same size as the frame buffer to store the shadow flag.
// Darkened a pixel in image generation if its shadow flag is on.
```

### Simple Ray Tracing for Collision

```
// a ray has been defined. 

for(each object in scene) {
    if(object is intersected and is the closest considered thus far)
    record intersection point and object id. 
}

// The recorded object is the closest and is the one being hit.
```

### Simple Ray Tracing for Collision(Voxelized)

```
// a ray has been defined.

Follow the ray's path
for each voxel in the path {
    if (a GO is in) {
        record it's ID
        break;
    }
}

// The recorded object is the closest and is the one being hit.
```

### Event-driven Programming

```
The event loop:

While (1) { // infinite loop
    event = getEvent(); // from the queue
    switch (event) {
        case Redisplay: display (); break; 
        case Keyboard: keyboard(); break; 
        case WindowResize: resize(); postEvent(Redisplay); break;
        default: idle(); 
    } 
}
```

### User Interfaces
- CLI (Command Line Input) is a text-based interface that allows users to input commands using a keyboard.
- GUI (Graphical User Interface) is a visual interface that allows users to interact with the computer using a mouse, touch screen, or other graphical elements.
- NUI (Natural User Interface) is an interface that allows users to interact with the computer using natural means of communication, such as gestures or voice commands.

### Virtual and Augmented Reality
- Virtual Reality (VR) is a computer-generated simulation of a three-dimensional environment that users can interact with.
- Augmented Reality (AR) is a technology that overlays digital information onto the real-world environment, usually viewed through a mobile device or headset.
- Mixed Reality (MR) is a blend of VR and AR that allows users to interact with both digital and physical objects in real time.

### Software for Graphics
- GDI
- OpenGL (webGl)
- OpenCl
- ActiveX 3D

### Flocking

```
rule1() is implementing the cohesion
Boids try to fly towards the centre of mass of neighbouring boids.

PROCEDURE rule1(boid bJ)
    Vector pcJ
    FOR EACH BOID b
        IF b != bJ THEN
            pcJ = pcJ + b.position
        END IF
    END FOR
    pcJ = pcJ / (N-1)
    RETURN (pcJ - bJ.position) / 100
END PROCEDURE

rule 2 Boids try to keep a small distance away from other objects (including other boids):

PROCEDURE rule2(boid bJ)
    Vector c = 0; # Declare a vector c to store the offset to move bJ away from other boids
    FOR EACH BOID b 
        IF b != bJ THEN 
            IF |b.position - bJ.position| < 100 THEN # Check if b is within a certain distance from bJ
            c = c - (b.position - bJ.position) # Add an offset to c that moves bJ away from b
            END IF
        END IF
    END FOR
    RETURN c # Return the vector offset to move bJ away from other boids
END PROCEDURE # End the function definition

Rule 3: Boids try to match velocity with near boids.

PROCEDURE rule3(boid bJ)
    Vector pvJ # Declare a vector pvJ to store the perceived velocity of all other boids
    FOR EACH BOID b  
        IF b != bJ THEN 
            pvJ = pvJ + b.velocity # Add the velocity vector of b to pvJ
        END IF
    END FOR
    pvJ = pvJ / N-1 # Calculate the average velocity vector of all other boids (excluding bJ)
    RETURN (pvJ - bJ.velocity) / 8 # Compute the vector offset to move bJ towards the perceived velocity and return it
END PROCEDURE 
```



