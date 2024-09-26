Here's a detailed README file for the **Dynamic Pathfinding with Real-time Data (DPRD) Algorithm** that you developed, based on the content of your PDF:

---

# Dynamic Pathfinding with Real-time Data (DPRD) Algorithm

## Introduction

The **Dynamic Pathfinding with Real-time Data (DPRD) Algorithm** is an innovative solution to the classic pathfinding problem, specifically designed to adapt to real-time traffic and weather conditions. This algorithm is based on traditional pathfinding approaches, such as Dijkstra's algorithm, but introduces the ability to dynamically adjust the weights of paths between cities in response to external factors like traffic congestion and weather changes. It aims to provide the most efficient route between cities by considering both the static distance between locations and the current environmental conditions.

## Algorithm Overview

### Key Features

1. **Graph Representation**: The algorithm models a network of cities as a graph, where:
   - Each city is a node.
   - Each road between cities is an edge with a base weight representing the fixed distance or time.
   
2. **Real-time Data Integration**: The algorithm dynamically adjusts the edge weights in real-time based on:
   - **Traffic conditions**: Captured from real-time APIs or randomly generated for simulation.
   - **Weather conditions**: Fetched from meteorological services or weather APIs.

3. **Caching Mechanism**: 
   - Results of path calculations are stored using a unique hash representing the current conditions.
   - If similar conditions are encountered, the cached result is retrieved, significantly reducing computational overhead.

4. **Dynamic Weights**:
   - The dynamic weight of each path is calculated using a formula that integrates the base distance, traffic levels, and weather conditions.
   - Traffic levels and weather categories both impose a percentage increase over the base distance.

### How the Algorithm Works

1. **Fixed Weights**: Initially, fixed weights (distances) are assigned to the edges in the graph, representing travel times or distances in the absence of traffic or weather conditions.

2. **Graph Construction**: A graph `G` is constructed with cities as nodes and roads as edges.

3. **Real-time Data Updates**: Traffic and weather conditions are fetched in real-time. These are used to dynamically adjust the weights of the edges.

4. **Dynamic Weight Calculation**: The final weight of an edge is calculated using the following formula:
   ```
   f(node) = d(node) + max(w(start node), w(end node)) + t(node)
   ```
   where:
   - `d(node)` is the base distance.
   - `w(node)` is the weather impact (percentage increase based on weather conditions).
   - `t(node)` is the traffic impact (percentage increase based on traffic levels).

5. **Caching Results**: Before recalculating a path, the algorithm checks the cache to see if the same traffic and weather conditions have been previously encountered. If a cached result is found, it is reused.

6. **Pathfinding with Dijkstra's Algorithm**: If no cached result is available, the algorithm calculates the shortest path using Dijkstra’s algorithm, taking the dynamic weights into account.

7. **Caching Mechanism**: The calculated path is then stored in the cache for future use, along with a hash representing the current conditions.

## Implementation Steps

### Step 1: Define Fixed Weights
- Base travel times or distances are assigned to the edges of the graph.
  
### Step 2: Graph Construction
- The network of cities is represented as a graph `G`, where each city is a node and each road is an edge.

### Step 3: Real-time Data Integration
- Traffic and weather data are gathered, either from APIs or generated randomly.

### Step 4: Dynamic Weight Calculation
- Edge weights are adjusted dynamically based on real-time conditions using the formula described above.

### Step 5: Pathfinding with Caching
- The algorithm checks if the current conditions have been encountered before by generating a hash value for the conditions. If so, the cached path is retrieved; otherwise, the path is calculated and cached.

### Step 6: Caching Mechanism
- All calculated paths are stored along with the corresponding conditions hash, allowing for faster retrieval during similar conditions in future queries.

### Step 7: Display and Use Cached Paths
- The cached paths are retrieved efficiently during repeated queries, reducing computational time and improving performance.

## Example of Algorithm in Action

Consider a network of six cities with predefined distances, weather, and traffic conditions. The algorithm adjusts travel times based on dynamic conditions, calculating the shortest path between the source and destination cities. For example, it calculates the least costly path from City A to City F by considering weather and traffic factors.

## Dependencies

- Python 3.x
- Libraries: `networkx`, `matplotlib`, `random`, `hashlib`, `heapq`


### License

```
This project is licensed under the @2024 Umar Mohammad
```
