To construct phylogenetic trees for the 1550 prokaryotic genomes we are interested in, we followed the procedure described by Ciccarelli, F. D. _et al_ (PMID: 16513982), with modifications.

Briefly,
  1. identify the 40 universally conserved marker genes using [fetchMG](http://vm-lux.embl.de/~mende/fetchMG/contact.html) for each of the 1550 genomes;
  1. saved the protein sequences into 40 files, one for each marker gene; in the end, we would have 40 files, each contains about 1550 protein sequences.
  1. align the protein sequences in each of the 40 files using MUSCLE. At the end of this step, we should have 40 multiple sequence alignment (MSA) files.
  1. refine the MSAs using Gblocks with parameters '-t=p -b3=8 -b4=2 -b5=h' (parameters recommended by Ciccarelli, F. D. _et al_)
  1. concatenate the 40 refined MSAs into one
  1. run RAxML on the resulting MSA using the JTT model ( -m PROTGAMMAJTT). A maximum likelihood (ML) tree will be obtained. This tree was rerooted at the last common ancestor of bacteria and archaea.
  1. (optional step) upload the resulting tree to [evolview](http://evolgenius.info/evolview) for visualisation.

preprocessed files for download:
| **file (download link)** | **description** |
|:-------------------------|:----------------|
|  [marker genes](https://drive.google.com/open?id=0BwieX-ApVZM5UkVQNnp0WjNoZlE&authuser=0)  | protein accession numbers of the marker genes identified in the 1550 genomes; there are four columns in the text file: 'genomeAcc' : accession number of genomes; 'proAcc' : accession number of protein sequences; 'hmmModel' : marker gene group; 'eValue' : e-value from hmm search |
|  [concatenated MSA](https://drive.google.com/open?id=0BwieX-ApVZM5WElGUWF2cG5EZVU&authuser=0) | concatenated multiple sequence alignment that was used to construct the phylogenetic tree  |
| [RAxML tree in newick format](https://drive.google.com/open?id=0BwieX-ApVZM5TFY2OHM4MWRQVEk&authuser=0) | resulting phylogenetic tree for the 1550 genomes in NHX format; the tree has branch lengths but no bootstrap values |
| [processed ULTRAMETRIC tree](https://drive.google.com/open?id=0BwieX-ApVZM5ZzBZWS14VTAwZTg&authuser=0) | processed tree using the chronos function (in the 'ape' package) in R |

**please contact me** (chenwh550@gmail.com) if you're interested in the protein sequences of the marker genes and the 40 MSAs before Glocks-ing and concatenation.