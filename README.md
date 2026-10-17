# ReaxFF Molecular Dynamics Model for Mg Metal/PrIm Electrolyte Interface

This repository provides the ReaxFF molecular dynamics input files, a full-size initial structural model, and the complete ReaxFF force-field file to facilitate reproducibility of the simulation methodology described in the manuscript:

**“ReaxFF-Enabled Atomistic Insights into Electrode/Electrolyte Interphase Evolution on Magnesium Metal Anodes”**

The deposited files provide the simulation setup and workflow for the full-size Mg metal/PrIm electrolyte interfacial model used in the manuscript.

## 1. Repository contents

```text
Mg_ReaxFF_simulations/
├── README.md
├── input_scripts_and_model/
│   ├── in.lmp
│   └── model.data
└── Reaction_Force_Field_File/
    └── reaxff_MgCHONSF.ffield
```

### `input_scripts_and_model/`

- `in.lmp`  
  LAMMPS input script for the ReaxFF molecular dynamics simulation.

- `model.data`  
  Full-size initial structural model containing the Mg metal slab and electrolyte region, with dimensions corresponding to the production model used in the manuscript.

### `Reaction_Force_Field_File/`

- `reaxff_MgCHONSF.ffield`  
  The complete ReaxFF parameter file containing the Mg/C/H/O/N/S/F elements required for the Mg(TFSI)₂-based electrolyte system.

## 2. Simulation system

The deposited model describes the **0.3 M Mg(TFSI)₂ in PrIm** electrolyte in contact with a Mg metal electrode at 300 K.

The deposited model is a full-size production model used in the manuscript. It contains a Mg(0001) slab approximately **100 Å thick** and an electrolyte region approximately **150 Å thick**. The lateral dimensions of the simulation cell are approximately **35 Å × 39 Å**.

The electrolyte composition and model construction procedure are described in detail in the Supplementary Information.

## 3. Boundary conditions and simulation protocol

Periodic boundary conditions were applied in all three directions. The simulation was performed using the ReaxFF reactive force field implemented in LAMMPS.

The simulation was conducted at **300 K**.

The ReaxFF simulations described in the manuscript were used to investigate interfacial processes including:

- solvent and anion decomposition;
- interphase formation and evolution;
- SEI thickness and density;
- organic/inorganic interphase components;
- Mg surface structural evolution; and
- gas-product formation.

Further methodological details are provided in the main manuscript and Supplementary Information.

## 4. Reproducing the full-size simulation

A compatible version of LAMMPS with ReaxFF support is required.

The full-size simulation can be initiated using the provided input script:

```bash
lmp -in in.lmp
```

The exact LAMMPS executable name may vary depending on the local installation.

Before running the calculation, please ensure that:

1. `model.data` is located in the working directory;
2. the ReaxFF force-field file is correctly referenced in `in.lmp`; and
3. the LAMMPS installation supports the required ReaxFF functionality.


## 5. Production trajectory files

The production trajectories generated from the full-size simulation models are substantially larger than the input files and force-field parameters and are therefore not included directly in this GitHub repository.

Instead, the repository provides the LAMMPS input script, the full-size initial structural model, and the complete ReaxFF force-field parameter file. These files allow the full-size simulation setup and force-field implementation to be inspected and the calculation to be reproduced.

Trajectory-derived results and analyses relevant to the manuscript are provided in the Supplementary Information.

## 6. Relation to the manuscript

The files in this repository are provided as a reproducibility package for the ReaxFF simulation methodology described in the manuscript.

In particular, the deposited `in.lmp`, `model.data`, and `reaxff_MgCHONSF.ffield` files provide the LAMMPS input, the full-size starting configuration, and the force-field parameters needed to inspect and reproduce the full-size simulation setup.
