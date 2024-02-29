# Dynamic Pathfinding with Real-time Data (DPRD) Algorithm

## Overview
The Dynamic Pathfinding with Real-time Data (DPRD) Algorithm is an innovative approach to route optimization within a network of cities. It dynamically integrates traffic and weather conditions into the shortest path calculation, ensuring that the chosen route is optimized for current conditions.

## Features
- **Dynamic Weight Adjustment**: Changes the importance of paths based on real-time traffic jams and weather conditions.
- **Real-time Data Integration**: Receives updates about traffic and weather, adjusting the route on the fly.
- **Caching Mechanism**: Stores paths with unique hash values for quick retrieval under similar conditions in the future.

## How It Works
1. **Graph Construction**: A graph representing a network of cities is created with nodes as cities and edges as roads.
2. **Data Integration**: Traffic and weather data are integrated into the algorithm.
3. **Dynamic Weight Calculation**: Weights of edges are adjusted dynamically based on current conditions.
4. **Pathfinding with Caching**: Dijkstra's algorithm is used for pathfinding, and results are cached for efficiency.
5. **Cached Path Retrieval**: Before recalculating a path, the cache is checked using the current conditions' hash value.

## Acknowledgments
Read the detailed report for understanding technical details of the algorithm.
