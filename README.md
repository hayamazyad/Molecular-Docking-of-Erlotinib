# Molecular Docking of Erlotinib with the EGFR Tyrosine Kinase Domain

This project investigates the molecular docking of Erlotinib (AQ4), an EGFR tyrosine kinase inhibitor, with EGFR's kinase domain (PDB ID: 1M17). EGFR is a critical regulator involved in cell growth and cancer development, making it a significant therapeutic target.

<div align="right" style="font-size:16px; color:black; font-family:Segoe UI, sans-serif;">
Developed by Haya Mazyad & Joudy Allam
    
As part of the *Computational Biology* course, December 2024
</div>

---
**The study involves**:
- Structural preparation of EGFR kinase domain and Erlotinib ligand
- Ligand cleaning, torsional flexibility, and charge assignment
- Grid box parameterization around the active site
- Docking simulations using AutoDock4 with Lamarckian Genetic Algorithm (LGA)
- Binding energy analysis, conformational clustering, structural alignment, and visualization

**This repository contains**:
- A comprehensive scientific report in PDF format detailing methodology, results, and structural analysis

## Objectives
1. Compare binding conformations and interaction energies of Erlotinib to EGFR kinase domain
2. Evaluate structural accuracy and pose prediction reliability
3. Visualize docking results and analyze ligand flexibility impact

## Receptor and Ligand Preparation
- Receptor (EGFR kinase domain, PDB: 1M17): Water molecules and alternate-location conformers removed; hydrogen atoms added; Kollman and Gasteiger charges computed.
- Ligand (Erlotinib, AQ4): Extracted from crystal structure; water removed; torsion tree root identified; 10 rotatable bonds assigned; Gasteiger charges computed.

## Docking Protocol
- Software: AutoDockTools 1.5.7, AutoDock4, UCSF Chimera, PyMOL
- Docking Algorithm: Lamarckian Genetic Algorithm (LGA)
- Grid Dimensions: 60 × 68 × 58 Å, spacing 0.375 Å
- Parameters:
   - 100 docking runs
   - Population size: 150
   - Max evaluations: 2,500,000
   - Mutation rate: 0.02
   - Crossover rate: 0.8
 
## Results

### Docking Results (Alternate A)
- Best binding energy: -7.23 kcal/mol (Run 67)
- Torsional energy: +2.983 kcal/mol
- Clustering: 25 clusters with RMSD ≤ 2.0 Å
- Most populated cluster: Cluster 1
- Key interactions:
    - Hydrogen bonds: MET769, CYS773
    - Hydrophobic interactions: ALA719, MET742
    - Electrostatic interactions: ASP831, GLU738
- RMSD with crystal structure: Best pose RMSD 1.95 Å (Run 67); better RMSD 1.39 Å (Run 76, energy -6.88 kcal/mol)

### Docking Results (Alternate B)
- Best binding energy: -7.27 kcal/mol (slightly better than alternate A)
- Mean binding energy: Higher (-6.27 kcal/mol) than alternate A (-6.67 kcal/mol)
- Observations: Alternate B poses exhibit greater variability in binding orientations, highlighting the impact of ligand conformational variants.

### Structural Comparison
- Docked structures align well with experimental (crystal) poses.
- Ligand flexibility significantly influences docking performance, illustrated by comparative analysis between Alternates A and B.

## Tools and Formats
- `.pdb` / `.pdbqt`: Receptor and ligand files
- `.gpf`, `.dpf`, `.map`, `.dlg`: AutoGrid and AutoDock parameter and output files
- `.pdf`: Comprehensive scientific docking report
- UCSF Chimera, PyMOL: Used for visualization, interaction analysis, and structural alignment
