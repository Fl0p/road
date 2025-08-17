# Maximum Houses Near Road - Interactive Grid Tool

An interactive web application for solving the optimal road placement problem to maximize the number of houses that can be built adjacent to the road.

## Problem Description

Given a rectangular grid of W × H cells, the goal is to design a road layout that maximizes the number of houses that can be placed on the grid. The constraints are:

- **Road connectivity**: The road must form a single connected component (4-connected, no diagonals)
- **Starting position**: The road always starts at position (0,0)
- **House placement**: Houses can only be placed in cells that are adjacent to at least one road cell (4-connected, no diagonals)
- **No overlap**: Houses cannot be placed on road cells

## Features

### Manual Road Drawing
- **Click to extend**: Click on empty cells adjacent to existing road to extend the road
- **Click to remove**: Click on road cells to remove them (only if it doesn't break road connectivity)
- **Visual hints**: 
  - Green glow indicates cells where road can be added
  - Orange glow indicates road cells that can be removed
  - Blue glow on hover for all interactive cells

### Automatic Optimization
- **Heuristic solver**: Fast beam search with lookahead for good solutions
- **Exact solver**: Branch-and-bound algorithm to find provably optimal solutions
- **Real-time progress**: Shows search progress and current best solution

### Interactive Interface
- **Adjustable grid size**: 2×2 to 15×15 grids
- **Live statistics**: 
  - Number of houses
  - Road length
  - Cell coverage percentage
  - Search nodes explored
- **Visual feedback**: Real-time updates of covered areas and house placements

## How to Use

1. **Set grid dimensions**: Adjust width and height (2-15 cells each)
2. **Manual drawing**: Click adjacent cells to build your road layout
3. **Automatic solving**: Use "Solve Optimally" for the best possible solution
4. **Reset**: Clear the grid and start over

## Technical Details

- **Algorithm**: Uses bitset operations for efficient state representation
- **Connectivity check**: BFS-based algorithm ensures road remains connected
- **Optimization**: Combines heuristic search with exact branch-and-bound
- **Performance**: Web Worker for non-blocking computation of optimal solutions

## File Structure

- `road.html` - Complete standalone application (HTML + CSS + JavaScript)

## Running the Application

Simply open `road.html` in any modern web browser. No additional dependencies or server setup required.

## Example Use Cases

- **Educational**: Understanding graph connectivity and optimization problems
- **Research**: Testing different road layout strategies
- **Game design**: Prototype for city-building or puzzle game mechanics
- **Algorithm comparison**: Benchmarking heuristic vs exact solution methods
