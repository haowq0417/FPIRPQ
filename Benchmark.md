# The benchmark queries used for FPIRPQ

The prefixes used:

```SPARQL
PREFIX ub: <http://www.lehigh.edu/~zhp2/2004/0401/univ-bench.owl#>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX dbo: <http://dbpedia.org/ontology/>
```


## 1. LUBM data sets

The 12 benchmark queries for PAIRPQ on [LUBM](http://swat.cse.lehigh.edu/projects/lubm/):


### Q1

```SPARQL
SELECT * WHERE {
	?x ub:publicationAuthor/ub:advisor ?y.
}
```

### Q2

```SPARQL
SELECT * WHERE {
	?x rdf:type ub:Publication.
  ?x ub:publicationAuthor/ub:advisor ?y.
}
```

### Q3

```SPARQL
SELECT * WHERE { 
	?x ub:worksFor / ub:subOrganizationOf ?y.
}
```

### Q4

```SPARQL
SELECT * WHERE {
	?x ub:publicationAuthor/ ub:advisor / ub:undergraduateDegreeFrom ?y.
}
```

### Q5

```sparql
SELECT * WHERE {
  ?x rdf:type ub:Publication.
	?x ub:publicationAuthor/ ub:advisor / ub:undergraduateDegreeFrom ?y.
}
```

### Q6

```SPARQL
SELECT * WHERE {
    ?x ub:publicationAuthor / ub:advisor / ub:worksFor ?y.
}
```

### Q7

```SPARQL
SELECT * WHERE {
	?x ub:publicationAuthor / ub:advisor / ub:name ?y.
}
```

### Q8

```SPARQL
SELECT * WHERE { 
	?x ub:worksFor/ub:subOrganizationOf+ ?y.
}
```

### Q9

```SPARQL
SELECT * WHERE { 
	?x ub:publicationAuthor/ ub:advisor/ (ub:undergraduateDegreeFrom |ub:teacherOf) ?y
}
```

### Q10

```SPARQL
SELECT * WHERE { 
	?x ub:publicationAuthor/ ub:advisor/ (ub:undergraduateDegreeFrom |ub:worksFor) ?y
}
```

### Q11

```SPARQL
SELECT * WHERE { 
    ?x ub:publicationAuthor / ub:advisor / ub:worksFor+ ?y
}
```

### Q12

```SPARQL
SELECT * WHERE {
    ?x ub:ub:advisor / (ub:publicationAuthor/ ub:advisor ) + ?y.
}
```


## 2. DBpedia data sets

The 12 benchmark queries for PAIRPQ on [DBpedia](https://www.dbpedia.org/):

### Q1

```SPARQL
SELECT * WHERE {
	?x dbo:birthPlace / dbo:isPartOf ?y
}
```

### Q2

```SPARQL
SELECT * WHERE {
    ?x rdf:type dbo:Athlete.
    ?x dbo:birthPlace / dbo:isPartOf ?y.
}
```

### Q3

```sparql
SELECT * WHERE {
    ?x dbo:knownFor / dbo:position ?y
}
```

### Q4

```SPARQL
SELECT * WHERE {
    ?x dbo:starring / dbo:birthPlace / dbo:isPartOf ?y
}
```

### Q5

```sparql
SELECT * WHERE {
    ?x rdf:type dbo:Athlete.
    ?x dbo:birthPlace / dbo:isPartOf /dbo:isPartOf ?y.
}
```

### Q6

```SPARQL
SELECT * WHERE {
    ?x dbo:birthPlace / dbo:isPartOf / dbo:knownFor ?y
}
```

### Q7

```SPARQL
SELECT * WHERE {
    ?x dbo:birthPlace / dbo:isPartOf / dbo:comment ?y
}
```

### Q8

```SPARQL
SELECT * WHERE {
    ?x dbo:isPartOf / dbo:knownFor + ?y
}
```

### Q9

```SPARQL
SELECT * WHERE {
    ?x dbo:isPartOf / dbo:isPartOf (dbo:isPartOf | dbo:location) ?y
}
```

### Q10

```sparql
SELECT * WHERE {
    ?x dbo:isPartOf / dbo:isPartOf (dbo:isPartOf | dbo:knownFor) ?y
}
```

### Q11

```SPARQL
SELECT * WHERE {
    ?x dbo:birthPlace / dbo:location / dbo:knownFor+ ?y
}
```

### Q12

```sparql
SELECT * WHERE {
    ?x dbo:knownFor /  (dbo:birthPlace / dbo:isPartOf)+ ?y
}
```
