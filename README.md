# ReaxFF Molecular Dynamics Model for Mg Metal/PrIm Electrolyte Interface

This repository provides the ReaxFF molecular dynamics input files, a representative initial structural model, and the complete ReaxFF force-field file to facilitate reproducibility of the simulation methodology described in the manuscript:

**“ReaxFF-Enabled Atomistic Insights into Electrode/Electrolyte Interphase Evolution on Magnesium Metal Anodes”**

The deposited files provide an accessible example of the simulation setup and workflow used for the Mg metal/electrolyte interface.

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
  Representative initial structural model containing the Mg metal slab and electrolyte region. The model is derived from the simulation configuration used in the study, with slightly reduced Mg slab and electrolyte thicknesses to facilitate reproduction of the simulation setup.

### `Reaction_Force_Field_File/`

- `reaxff_MgCHONSF.ffield`  
  The complete ReaxFF parameter file containing the Mg/C/H/O/N/S/F elements required for the Mg(TFSI)₂-based electrolyte system.

## 2. Simulation system

The deposited model describes the **0.3 M Mg(TFSI)₂ in PrIm** electrolyte in contact with a Mg metal electrode at 300 K.

The Mg metal electrode is represented by a Mg(0001) slab with an approximately **85 Å thickness**, while the electrolyte region is approximately **100 Å thick**. The lateral dimensions of the simulation cell are approximately **35 Å × 39 Å**.

The deposited model is based on the same simulation configuration used in the study, with the Mg slab and electrolyte region slightly reduced in thickness for computational convenience. The full-size production models used in the manuscript contain an approximately **100 Å Mg slab and 150 Å electrolyte region**.

The electrolyte composition and model construction procedure are described in detail in the Supplementary Information.

## 3. Boundary conditions and simulation protocol

Periodic boundary conditions were applied in the all three directions. The simulation was performed using the ReaxFF reactive force field implemented in LAMMPS.

The representative simulation was conducted at **300 K**.

The ReaxFF simulations described in the manuscript were used to investigate interfacial processes including:

- solvent and anion decomposition;
- interphase formation and evolution;
- SEI thickness and density;
- organic/inorganic interphase components;
- Mg surface structural evolution; and
- gas-product formation.

Further methodological details are provided in the main manuscript and Supplementary Information.

## 4. Reproducing the representative simulation

A compatible version of LAMMPS with ReaxFF support is required.

The representative simulation can be initiated using the provided input script:

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

Instead, the repository provides the LAMMPS input script, the representative initial structural model, and the complete ReaxFF force-field parameter file. These files allow the simulation setup and force-field implementation to be inspected and a representative calculation to be reproduced without requiring the large production trajectory files.

Trajectory-derived results and analyses relevant to the manuscript are provided in the Supplementary Information.

## 6. Relation to the manuscript

The files in this repository are provided as a reproducibility package for the ReaxFF simulation methodology described in the manuscript.

In particular, the deposited `in.lmp`, `model.data`, and `reaxff_MgCHONSF.ffield` files provide the LAMMPS input, a representative starting configuration, and the force-field parameters needed to inspect and reproduce the representative simulation setup.
