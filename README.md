# taxonomy-merging
Scripts for running and preparing input to the [ALA Taxonomy builder and nameindexer](https://github.com/AtlasOfLivingAustralia/documentation/wiki/A-Guide-to-Getting-Names-into-the-ALA). These tools may be used to merge the [GBIF taxonomy backbone](https://www.gbif.org/dataset/d7dddbf4-2cf0-4f39-9b2a-bb099caae36c) with the [Genome Taxonomy DataBase (GTDB) taxonomy](https://gtdb.ecogenomic.org/about), and with a list of Swedish Amplicon Sequence Variants (ASVs), to improve taxonomic coverage of prokaryotes in the BioAtlas. 

## Overview of files

*get-bb-subset.sh*, *prep-gtdb-for-r.sh* <br>make subsets of GBIF backbone / GTDB taxonomy -> manageable size & structure for further editing i R

*prep-xxx-for-merge.R* <br>edits data, and adds parent taxa -> file suitable for ALA Taxonomy builder

*merge-taxonomy.sh* <br>applies ALA Taxonomy builder, and outputs zip file to be transferred to the BioAtlas

## Taxonomy implementation in the BioAtlas
Notes below describe how to implement the merged taxonomy in a test version of the BioAtlas, and assumes that scp & ssh connection options (host, user, RSA key file) are specified in a *.ssh/config file*, allowing us to use an alias (here: *cloud*) for connections.

1. Copy taxonomy-dwca to server

```console

scp ~/data/lucene/runs/xxx/dyntaxa.dwca.zip cloud:repos/ala-docker/dyntaxa-index

```

## References
Parks, D. H., et al. (2018). "A standardized bacterial taxonomy based on genome phylogeny substantially revises the tree of life." Nature Biotechnology, 36: 996-1004.


