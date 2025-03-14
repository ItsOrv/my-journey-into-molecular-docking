# Step 4: Analysis & Results

Now comes the best part—analyzing the results of your docking experiment. This is where you figure out how well your ligand binds to the protein and what it might mean for further research.

## Opening Your Results
- **Output File:**  
  Use visualization tools like PyMOL or AutoDock Tools to open your `output.pdbqt` file. This lets you see the docked poses and binding sites in detail.
- **Jupyter Notebooks:**  
  I’ve added some notebooks in the `notebooks/` folder to help parse and visualize the results.

## How to Analyze
1. **Visual Inspection:**  
   Look at the binding poses and check for interactions like hydrogen bonds and hydrophobic contacts.
   
2. **Scoring:**  
   AutoDock Vina gives a binding affinity score. Lower (more negative) values usually mean a better binding fit.
   
3. **Comparisons:**  
   If you run multiple experiments, compare the scores and binding modes to see which setup works best.

## Using PDB and PubChem
- **PDB:**  
  The [Protein Data Bank](https://www.rcsb.org/) is your go-to for high-quality protein structures. Use it to confirm the accuracy of your protein models.
  
- **PubChem:**  
  For ligands, [PubChem](https://pubchem.ncbi.nlm.nih.gov/) provides detailed chemical properties. This info can help explain why certain interactions occur.

Analyzing your results is about being curious and trying different approaches until you get the best insights. Don’t hesitate to experiment with various parameters or tools until you find what works best for you.
