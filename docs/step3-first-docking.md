# Step 3: Running Your First Docking Experiment

Alright, now that everything’s set up, let’s get hands-on with our first docking experiment. This step is all about executing a simple docking run and checking out how our molecules interact.

## Preparing Your Files

1. **Get Your Protein & Ligand:**
   - Download a protein structure from [PDB](https://www.rcsb.org/). Pick one that looks interesting.
   - Grab a ligand file from [PubChem](https://pubchem.ncbi.nlm.nih.gov/) or create one yourself. Create one yourself? That sounds like a fun project! Maybe I'll dive into that later and set up a whole new repo for it.
     

## 2. File Formats: Converting Your Files

Before running the docking experiment, you need to make sure your protein and ligand files are in the correct format.

---

### **Protein File Preparation**
1. **Open AutoDock Tools (ADT)**  
   - Run the software using the terminal:  
     ```bash
     adt
     ```
   - Alternatively, open it from your application menu.

2. **Load the Protein File**  
   - Go to **File → Read Molecule** and select your downloaded **PDB** file.

3. **Remove Unnecessary Molecules**  
   - In the **Edit** menu, choose **Delete Water** to remove water molecules.
   - If any unwanted ligands or cofactors exist, go to **Select → Select From String**, enter the residue name (e.g., "LIG"), and press **Delete**.

4. **Add Polar Hydrogens**  
   - Go to **Edit → Hydrogens → Add** and select **Polar Only**.  
   - This step ensures correct hydrogen bonding interactions.

5. **Assign Gasteiger Charges**  
   - Go to **Edit → Charges → Compute Gasteiger**.  
   - This ensures the correct electrostatic properties for docking.

6. **Save as PDBQT**  
   - Go to **Grid → Macromolecule → Choose** and select the protein structure.  
   - Then, go to **File → Save as PDBQT** and name it **`protein.pdbqt`**.

---

### **Ligand File Preparation**
1. **Obtain the Ligand File**  
   - Download the ligand from **PubChem** or another source in **SDF** or **MOL2** format.

2. **Convert to PDB Format (If Needed)**  
   - Use OpenBabel to convert it to PDB:
     ```bash
     obabel input.sdf -O output.pdb
     ```
   - Alternatively, you can use ADT:
     - **File → Read Molecule** → Open your **MOL2/SDF** file.
     - **File → Save As** → Choose **PDB format**.

3. **Prepare the Ligand in ADT**
   - Load the PDB file (**File → Read Molecule**).
   - Go to **Edit → Hydrogens → Add** and select **All Hydrogens**.
   - Go to **Edit → Charges → Compute Gasteiger**.

4. **Convert to PDBQT**  
   - Go to **Ligand → Output → Save as PDBQT** and name it **`ligand.pdbqt`**.

---

If you're more comfortable with graphical interfaces, ADT makes it easy to prepare files. But learning command-line methods can save time, especially for batch processing in larger projects.
