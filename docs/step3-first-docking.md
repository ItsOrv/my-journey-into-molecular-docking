# Step 3: Running Your First Docking Experiment

Alright, now that everything’s set up, let’s get hands-on with our first docking experiment. This step is all about executing a simple docking run and checking out how our molecules interact.

## Preparing Your Files

**Get Your Protein & Ligand:**
   - Download a protein structure from [PDB](https://www.rcsb.org/). Pick one that looks interesting.
   - Grab a ligand file from [PubChem](https://pubchem.ncbi.nlm.nih.gov/) or create one yourself. Create one yourself? That sounds like a fun project! Maybe I'll dive into that later and set up a whole new repo for it.
     
## **1. Preparing the Protein and Ligand (PDBQT Format)**  

### **Graphical Method (Using AutoDockTools - ADT)**  
1. **Open AutoDockTools (ADT)**  
   - Run in terminal:  
     ```bash
     adt
     ```
   - Or open it from the applications menu.  

2. **Load the Protein**  
   - Go to **File → Read Molecule** and select `protein.pdb`.  

3. **Remove Water Molecules (Optional but Recommended)**  
   - Go to **Edit → Delete Water**  

4. **Add Polar Hydrogens**  
   - **Edit → Hydrogens → Add Polar Only**  

5. **Compute Charges**  
   - **Edit → Charges → Compute Gasteiger**  

6. **Save as PDBQT**  
   - **File → Save As → protein.pdbqt**  

### **Command-Line Method**  
```bash
prepare_receptor4.py -r protein.pdb -o protein.pdbqt
```

---

### **Preparing the Ligand**  
The steps are similar to protein preparation.  

- **In ADT:**  
  - **File → Read Molecule** (select `ligand.pdb`)  
  - **Edit → Hydrogens → Add All**  
  - **Edit → Charges → Compute Gasteiger**  
  - **Ligand → Torsion Tree → Detect Root** (for flexible ligands)  
  - **File → Save As → ligand.pdbqt**  

- **In the terminal:**  
  ```bash
  prepare_ligand4.py -l ligand.pdb -o ligand.pdbqt
  ```

---

## **2. Setting Up the Grid Box**  

### **Graphical Method (Using ADT)**  
1. **Open the Grid Box Setup**  
   - **Grid → Grid Box**  
2. **Adjust Size and Position**  
   - Set **X, Y, Z center** and **size_x, size_y, size_z** based on the binding site.  
3. **Save the Grid Box Configuration**  
   - **File → Save Grid Box** as `config.txt`.  

### **Command-Line Method**  
You can manually create `config.txt`:  
```txt
receptor = protein.pdbqt
ligand = ligand.pdbqt
center_x = 10.5
center_y = 15.2
center_z = -5.3
size_x = 20
size_y = 20
size_z = 20
out = output.pdbqt
log = log.txt
```

---

## **3. Running the Docking**  

### **Graphical Method (Using ADT)**  
1. **Open AutoDock Vina**  
   - **Run → Docking → Open Vina**  
2. **Load Files**  
   - Select `protein.pdbqt` and `ligand.pdbqt`.  
3. **Load Grid Box**  
   - Click **Load Grid Box** and select `config.txt`.  
4. **Run Docking**  
   - Click **Run Vina** and wait for the results.  
5. **Save Output**  
   - Save the output as `output.pdbqt`.  

### **Command-Line Method**  
```bash
vina --config config.txt
```
or  
```bash
vina --receptor protein.pdbqt \
     --ligand ligand.pdbqt \
     --center_x 10.5 --center_y 15.2 --center_z -5.3 \
     --size_x 20 --size_y 20 --size_z 20 \
     --out output.pdbqt --log log.txt
```

---

## **4. Analyzing the Results**  

### **Graphical Method (Using PyMOL or ADT)**  
1. **Open PyMOL**  
   ```bash
   pymol
   ```
2. **Load Files**  
   - **File → Open** and select `protein.pdb` and `output.pdbqt`.  
3. **Analyze Interactions**  
   - Use **align** or **superposition** to check ligand binding.  

### **Command-Line Method**  
Check docking scores:  
```bash
grep '^REMARK VINA RESULT' log.txt
```
Get the top five results:  
```bash
cat log.txt | grep "REMARK VINA RESULT" | sort -k4,4g | head -5
```

---
That's it! You've successfully completed a full docking workflow using both graphical and command-line methods.  

If you're more comfortable with graphical interfaces, ADT makes it easy to prepare files. But learning command-line methods can save time, especially for batch processing in larger projects.
