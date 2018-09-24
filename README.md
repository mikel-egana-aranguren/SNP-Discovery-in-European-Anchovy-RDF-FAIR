# SNP-Discovery-in-European-Anchovy-RDF-FAIR

Los resultados de la investigación descrita en el artículo "SNP Discovery in European Anchovy (Engraulis encrasicolus, L) by High-Throughput Transcriptome and Genome Sequencing" (doi: 10.1371/journal.pone.0070051) describen las secuencias usadas para descubrir SNPs en la anchoa. Estos datos contienen secuencias en formato tabular, cuyo consumo se ve limitado por este mismo formato. Así, las tablas han sido convertidas a RDF, usando principalmente dos ontologías de amplio uso:

Sequence Ontology: https://bioportal.bioontology.org/ontologies/SO
Uniprot ontology: https://www.uniprot.org/core/

Esto permite hacer consultas más sofisticadas de los datos, como la siguiente:

```
SELECT * WHERE { 
    ?motif <http://lod.eurohelp.es/Sequence> ?sequence .
	?motif <http://purl.uniprot.org/core/organism> ?taxon .
    FILTER(CONTAINS(?taxon, "Salmo"))
} 
```