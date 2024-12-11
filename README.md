# _benchmarking_state-reproducibility

#### Authors: Maria Rosaria Nucera, Cal McCrimmon, Davide Vespasiani, Kaan Öcal, Trevor Atkeson.

Aims:
- [x] Testing reproducibility of the pseudotime across the 3 different lines  (FSA0024I1, IST2607K3, WAB0137L8) using genes2genes to align and compare trajectories
- [x] Testing robustness to different criteria for the choice of the root (starting point of differentiation) based on expression of markers for pluripotency/other sets of markers
- [x] Testing what happens when the root starts from cells in a different cell cycle phase (G2M or S)
- [ ] Testing robustness to different number of cells x time point across the lines and whether this affects the trajectory or not


Tools and functions used during the Hackathon
| Package/function | Function |   Example |    
| ------------- | ------------- | ------------- |
|  [module_score(gene set)](https://pages.github.com/](https://scanpy.readthedocs.io/en/stable/generated/scanpy.tl.score_genes.html) | define start of trajectory |  |
|  [scFates](https://pages.github.com/](https://scfates.readthedocs.io/en/latest/) | compute pseudotime |  |
|  [Genes2genes](https://pages.github.com/](https://github.com/Teichlab/Genes2Genes)| align pseudotime |  |

Workflow for Testing reproducibility of the pseudotime across the 3 different lines
```mermaid
graph TD;
    Line FSA0024I1 --> Pseudotime for the line FSA0024I1 computed with scFates;
    Line IST2607K3 --> Pseudotime for the line IST2607K3 computed with scFates;
    Line WAB0137L8 --> Pseudotime for the line WAB0137L8 computed with scFates;
    Pseudotime for the line FSA0024I1 computed with scFates-->Genes2Genes trajectory alignemnt;
    Pseudotime for the line IST2607K3 computed with scFatese-->Genes2Genes trajectory alignemnt;
    Pseudotime for the line WAB0137L8 computed with scFates-->Genes2Genes trajectory alignemnt;
    Genes2Genes trajectory alignemnt--> Identification of genes with differential dynamic expression;
   
```
