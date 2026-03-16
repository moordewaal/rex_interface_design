# Rosetta Workflow – Alanine Scanning

## Input structure
PDB: `4LC9.pdb`

---

## 1. Clean and relax structure

Clean PDB:
Remove lines that do not start with ATOM

Relax structure:

```bash
relax.static.macosclangrelease @flags_relax
```

Output: structure with lowest total_score after relaxation

```
4LC9_relax.pdb
```

---

## 2. Alanine scanning

Command:

```bash
rosetta_scripts.static.macosclangrelease \
 -s 4LC9_relax.pdb \
 -parser:protocol ala_scan.xml \
 -database ~/Software/rosetta/main/database
```

Output files:

```
score.sc
mutation_results.sc
```

---

## Files used

```
flags_relax
ala_scan.xml
```