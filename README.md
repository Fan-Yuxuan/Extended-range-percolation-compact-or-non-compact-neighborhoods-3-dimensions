# Code and Data for Extended-range percolation on lattices with compact and non-compact neighborhoods in three dimensions

This repository contains the official source code and experimental datasets used to generate the results presented in the paper.

## Repository Structure

# Experimental raw data (.txt)
```bash
.
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
n]
├── README.md               # This file
└──
```

# Dependencies & Compilation & Data Descri
To compile and run the C++ codes, ensure you have the following installed on your system:
Compiler: g++ (version 9.0 or later) or any C++17-compliant compiler.
Libraries: Standard Template Library (STL) only.
To compile the main analysis code, navigate to the cpp file and run:

```bash
g++ -mcmodel=medium -o main main.cpp
```

# Data Description

The experimental data are stored as plain text files (.txt). Each file corresponds to somes distinct experimental runs. The format of each results is as follows:

· Types of lattices (e.g., CUB-(2), SC-1,...)

· s^(τ-2)*(P≥s) versus s^σ in each p and slope (two tables presented respectively) 
