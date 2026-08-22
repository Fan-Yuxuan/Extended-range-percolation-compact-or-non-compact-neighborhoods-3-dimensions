# Code and Data for Extended-range percolation on lattices with compact and non-compact neighborhoods in three dimensions

This repository contains the official source code and experimental datasets used to generate the results presented in the paper.

## Repository Structure

```bash

# Experimental raw data (.txt)

│   ├── bond_cube_shaped_neighbors.txt
│   ├── site_cube_shaped_neighbors.txt
│   └── correspond to PART III
│   ├── site_non_compact_neighbors_SC.txt
│   ├── site_non_compact_neighbors_FCC.txt
│   ├── site_non_compact_neighbors_BCC.txt
│   └── correspond to PART IV

# C++ source codes (.cpp)

│   ├── bond_cube_shaped.cpp   
│   ├── site_cube_shaped.cpp
│   └── correspond to PART III
│   └── site_non_compact.cpp 
│   └── correspond to PART IV


├── README.md               # This file
└──
```

# Dependencies & Compilation
To compile and run the C++ codes, ensure you have the following installed on your system:

Compiler: g++ (version 9.0 or later) or any C++17-compliant compiler.

Libraries: Standard Template Library (STL) only.

To compile the main analysis code, navigate to the cpp file and run:

```bash
g++ -mcmodel=medium -o main main.cpp
```

In site_cube_shaped.cpp and bond_cube_shaped.cpp,there are two parameters can be changed in row 32 and 35:

```bash
#define PROB p        // bond probability in the plane
#define LENGTH L //  (~ - 1 = )cubic length,z = LENGTH*LENGTH*LENGTH-1, L only can be odds
```

By changing the two parameters, you can reproduce all of the data in bond_cube_shaped_neighbors.txt and site_cube_shaped_neighbors.txt. 

For example, calculating bond percolation on 6*6*6 cube-shaped neighborhoods with p=0.03092, you can exert bond_cube_shaped.cpp after changing the parameters into:

```bash
#define PROB 0.03092        // bond probability in the plane
#define LENGTH 7 //  (~ - 1 = )cubic length,z = LENGTH*LENGTH*LENGTH-1, L only can be odds
```

In site_non_compact.cpp, there are six parameters:

```bash
#define PROB p        // bond probability in the plane
#define LENGTH1 1 or 0 // Nth nearest neighbor's distance^2 to the center, NN-12345 ~ 11111, NN-1235 ~ 11101, NN-235 ~01101
#define LENGTH2 1 or 0
#define LENGTH3 1 or 0
#define LENGTH4 1 or 0
#define LENGTH5 1 or 0
...
if(LENGTH1) if (x*x + y*y + z*z == a1) ...
if(LENGTH2) if (x*x + y*y + z*z == a2) ...
if(LENGTH3) if (x*x + y*y + z*z == a3) ...
if(LENGTH4) if (x*x + y*y + z*z == a4) ...
if(LENGTH5) if (x*x + y*y + z*z == a5) ...
```

In SC lattice, a1-a5 corresponds to 1, 2, 3, 4, 5.

2, 4, 6, 8, 10 and 3, 4, 8, 11, 12 respectively corresponds to FCC and BCC lattices.

If you want to reproduce this code, firstly, you should choose the type of lattice then change the parameter a1~a5 to the lattice you choose.

then print your PROB and LENGTH1-5, for example, the parameters of FCC-125 are as follows:

```bash
#define PROB p        // bond probability in the plane
#define LENGTH1 1 // Nth nearest neighbor's distance^2 to the center, NN-12345 ~ 11111, NN-1235 ~ 11101, NN-235 ~01101
#define LENGTH2 1
#define LENGTH3 0
#define LENGTH4 0
#define LENGTH5 1
...
if(LENGTH1) if (x*x + y*y + z*z == 2) ...
if(LENGTH2) if (x*x + y*y + z*z == 4) ...
if(LENGTH3) if (x*x + y*y + z*z == 6) ...
if(LENGTH4) if (x*x + y*y + z*z == 8) ...
if(LENGTH5) if (x*x + y*y + z*z == 10) ...
```

# Data Description

The experimental data are stored as plain text files (.txt). Each file corresponds to somes distinct experimental runs. The format of each results is as follows:

· Types of lattices (e.g., CUB-(2), SC-1,...)

· s^(τ-2)*(P≥s) versus s^σ in each p and slope (two tables presented respectively) 
