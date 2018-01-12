# Mini-Minecraft
  Created a mini minecraft, using C++ and Qt, group of 3.
  
  Final demo: https://www.youtube.com/watch?v=eVyGlMWNpTg

Responsible for procedural terrain generation, L-system rivers generation, procedural biomes generation and random assets generation based on biomes.

## Procedural Terrain
- Using Fractal Brownian Motion noise to generate terrains.
- Class TerrainManager is used to generate and manage terrains, while converting world coordinates to local coordinates in every terrain.
- Meanwhile, implement add and delete one block by setting block type in terrain manager.

## L-System Rivers
- Using L-system and two different rules to generate two rivers, one is starting from (0, 0) and another's startpoint is (250, 250). Rivers' initial directions are generated through random numbers.
- L-system string rules and Class Turtle are used to draw rivers. Declaration and definition are in rivergenerate.h and rivergenerate.cpp
- Use river segments to make sure that rivers are continuous across terrains.

## Biomes Generation and Procedural Placed Assets
- Use worley noise to divide biomes on a map (a map contains 12 * 12 terrains), currently has ocean, beach, grassland, forest, bare and snow biomes. Maps are smoothly connected and no boundary for whole world.
- Reconstruct height mapping use Gaussian distribution and fractal Brownian Motion, which makes biomes more reasonable.
- Create assets. Currently has stonehill(actually ice hill), mushroom, tree, grass and cactus. They can be placed according to current biomes with certain probabilities. Changed texture create method to make mushroom and grass.
- Re-placed rivers. Both of them are melted from snow on the top of the hill and one merges to ocean, while another becomes delta rivers in forest area.
