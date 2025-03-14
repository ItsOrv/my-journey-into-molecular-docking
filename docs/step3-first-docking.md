# Step 3: Running Your First Docking Experiment

Alright, now that everything’s set up, let’s get hands-on with our first docking experiment. This step is all about executing a simple docking run and checking out how our molecules interact.

## Preparing Your Files

1. **Get Your Protein & Ligand:**
   - Download a protein structure from [PDB](https://www.rcsb.org/). Pick one that looks interesting.
   - Grab a ligand file from [PubChem](https://pubchem.ncbi.nlm.nih.gov/) or create one yourself.

2. **File Formats:**
   Ensure your protein file is in PDB format and convert it to PDBQT (if needed) using AutoDock Tools. Do the same for your ligand file.

## Running the Docking Experiment

Here’s a basic command using AutoDock Vina:
```bash
vina --receptor protein.pdbqt --ligand ligand.pdbqt --center_x 0 --center_y 0 --center_z 0 --size_x 20 --size_y 20 --size_z 20 --out output.pdbqt
```
- **Parameters Explained:**
  - `--center_x, --center_y, --center_z`: Set the center of the docking grid.
  - `--size_x, --size_y, --size_z`: Define the dimensions of your grid box.

Feel free to adjust these values based on your protein’s binding site.

## Some Tips
- **Double-Check Conversions:** Wrong file formats can mess things up.
- **Experiment:** Tweak the grid parameters and see how the results change.
- **Backup Your Files:** Always keep a copy of your original data in the `data/` folder.

Once the run is complete, you'll have an `output.pdbqt` file with your docked poses. We’ll analyze that next!
