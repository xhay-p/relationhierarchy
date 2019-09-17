# Taxonomical hierarchy of canonicalized relations from multiple Knowledge Bases
Paper: [Taxonomical hierarchy of canonicalized relations from multiple Knowledge Bases](https://arxiv.org/abs/1909.06249) <br>
Website: [Relation Hierarchy](https://relationhierarchy.github.io/)
<br><br>
## Abstract
This work addresses two important questions pertinent to Relation Extraction (RE). First, what are all possible relations that could exist between any two given entity types? Second, how do we define an unambiguous taxonomical (_is-a_) hierarchy among the identified relations? To address the first question, we use three resources Wikipedia Infobox, Wikidata, and DBpedia. This study focuses on relations between _person_, _organization and _location_ entity types. We exploit Wikidata and DBpedia in a data-driven manner, and Wikipedia Infobox templates manually to generate lists of relations. Further, to address the second question, we canonicalize, filter, and combine the identified relations from the three resources to construct a taxonomical hierarchy. This hierarchy contains 623 canonical relations with highest contribution from Wikipedia Infobox followed by DBpedia and Wikidata. The generated relation list subsumes an average of 85% of relations from RE datasets when entity types are restricted.

## Resources
* **Hierarchy Visualtion** ([Check Website](https://relationhierarchy.github.io/)): We have provided different hierarchies based on the source knowledge base(or combination of Knowledge bases).
  * __Dbpedia, Wikipedia, and Wikidata__: individual hierarchies for _person_, _location_, and _organization_ along with the complete hierarchy.
  * __Dbpedia Wikidata__: A joint hierarchy for the relations collected from both Dbpedia and Wikidata. Hierarchy can be visualised either radially or in spiral radial tree.
  * __Dbpedia Wikidata Infobox__: A joint hierarchy for the relations collected from both Dbpedia, Wikidata and Wikipedia Infobox templates. Hierarchy can be visualised either radially or in spiral radial tree.
* **relation.csv**: This csv file contains final list of 623 relations. Every line is of the form, [_source-entity-type_._target-entiy-type_.[_...ancestor-relations..._].relation
```
per.per.student
```
In above example, source entity type is _person_, target entity type is _person_, and relation is _student_.

```
per.per.student.doctoralStudent
```
In the above example, relation of interest is _doctoralStudent_ and it has one ancestor relation, _student_.
* **relation_id.csv**: This csv file contains all the relation following hierarchical visualization ([Radial tree](https://observablehq.com/@d3/radial-tidy-tree)/[Tidy tree](https://observablehq.com/@d3/cluster-dendrogram?collection=@d3/d3-hierarchy)). Every line contains the relation path from root node to the relation itself and unique relation id.
```
rel.per.per-org.associatedWith.institution.professorshipAt,R10300210
```
In the above example, _rel_ is the root node (common for all), _professorshipAt_ is the relation of interst, and _per_ (implies, person specific relation), _per-org_ (implies, source (_person_) and target (_organization_) entity types ), _associatedWith_, and _institution_ are intermdiary nodes/ancestor relations (genralisation). And _R10300210_ is the unique id assigned to the relation path.
