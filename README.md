# A Knowledge Graph of Clinical Trials (CTKG)

Clinical Trials Knowledge Graph (CTKG) is a knowledge graph constructed over the clinical trial data from The Access to Aggregate Content of ClinicalTrials.gov (AACT) database[^1]. CTKG includes nodes representing medical entities in clinical trials (e.g., studies, drugs, conditions), and edges representing the relations among these entities (e.g., drugs used in studies). It includes 1,496,684 nodes belonging to 18 node-types; and 3,667,750 triplets belonging to 21 relation-types. It also provides three notebooks about how to explore and analysis the CTKG using the knowledge graph embeddings.

This work has been published in Scientific Reports (https://www.nature.com/articles/s41598-022-08454-z).



<img src=".\Schema.png" alt="Schema" style="zoom:40%;" />



### CTKG dataset

The directory <code>rawdata</code> contains all the entities and relations:

* <code>attributes.zip</code> : the attributes of entities (e.g., "study").
* <code>relations.zip</code> : the attributes of relations between two types of entities (e.g., "study"--- study-condition ---"condition").
* <code>reverse.zip</code> : the attributes of reverse relations between two types of entities (e.g., "condition" --- condition-study --- "study").

### Embedding analysis

The directory <code>scripts</code> contains all the jupyter notebooks for the embedding analysis:

* <code>loading_ctkg_in_dgl.ipynb</code> is a notebook to load CTKG as a graph using the Deep Graph Library (https://www.dgl.ai/).
* <code>Train_embeddings.ipynb</code> is a notebook to generate the embeddings for nodes and relations in CTKG.
* <code>Subtype_entity_similarity_analysis.ipynb</code> is a notebook to retrieve similar nodes of a certain node type.
* <code>Crosstype_entity_similarity_analysis.ipynb</code> is a notebook for the drug repurposing analysis in the manuscript.

Before running the scripts, you need to unzip rawdata/ctkg.zip and rawdata/attributes.zip, and install DGL (https://www.dgl.ai/) and PyTorch. 
If you are not able to learn embeddings via the command in the notebook, please run the command in a terminal with DGL 0.4.3.  



### Citation

```
@Article{ctkg,
  author    = {Ziqi Chen and Bo Peng and Vassilis N. Ioannidis and Mufei Li and George Karypis and Xia Ning},
  journal   = {Scientific Reports},
  title     = {A knowledge graph of clinical trials (CTKG)},
  year      = {2022},
  month     = {mar},
  number    = {1},
  volume    = {12},
  doi       = {10.1038/s41598-022-08454-z},
  publisher = {Springer Science and Business Media {LLC}},
}
```



# Reference

[^1]: Tasneem A, Aberle L, Ananth H, Chakraborty S, Chiswell K, McCourt BJ, et al. (2012) The Database for Aggregate Analysis of ClinicalTrials.gov (AACT) and Subsequent Regrouping by Clinical Specialty. PLoS ONE 7(3): e33677. https://doi.org/10.1371/journal.pone.0033677

