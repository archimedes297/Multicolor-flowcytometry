# Multicolor Flow Cytometry Analysis — question-driven notebook

`flu_flow_cytometry_analysis.ipynb` is a fully-executed Jupyter notebook (outputs + figures embedded)
demonstrating the complete multicolor flow cytometry analysis toolkit and applying it to concrete
immunology questions about **B cells, germinal centers (incl. ectopic / tertiary-lymphoid), and the
influenza-vaccine antibody (HAI titer) response**.

## What's inside
- **Part A — real data:** a genuine **BD LSR II** `.fcs` file (shipped with `fcsparser`): FCS I/O &
  metadata, compensation with the embedded spillover matrix, arcsinh + logicle transforms, QC
  (margin + time-stability), manual sequential gating with a gating hierarchy, GMM auto-gating,
  quadrant/MFI, PCA/t-SNE, and KMeans/GMM/hierarchical/Leiden/FlowSOM clustering with a phenotype heatmap.
- **Part B — biology:** a biologically-grounded influenza-vaccine cohort (30 subjects, day 0/7/28,
  paired HAI titers, tissue ectopic GCs) answering six questions with statistical inference:
  plasmablast kinetics (Q1), HA-specific B cells (Q2), cellular→titer prediction (Q3), responder
  classification (Q4), dark/light-zone polarity of ectopic GCs + GC↔titer link (Q5), and unbiased
  differential abundance with FDR (Q6).

## Run / re-run
```
pip install -r requirements.txt
jupyter notebook flu_flow_cytometry_analysis.ipynb   # Kernel ▸ Restart & Run All
```
Open `flu_flow_cytometry_analysis.html` to view all outputs without Jupyter.

## Data provenance
The BD LSR II file is **real instrument data**. The cohort is **simulated** (documented generative
model) because public repositories with matched vaccine flow + titer data (FlowRepository, ImmPort,
Zenodo) were network-blocked during the build; the notebook's final section shows the one-line loader
change to point the same pipeline at real downloaded FCS + a titer table. The cohort is for
demonstration only and is not real patient data.
