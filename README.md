# hdh-cafe-con-2023
Proyecto para actividad HDH "Café con" con la Asociación de Humanidades Digitales Hispánicas

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/hibernator11/hdh-cafe-con-2023/HEAD)

[![DOI](https://zenodo.org/badge/620414822.svg)](https://zenodo.org/badge/latestdoi/620414822)

<img src="imagenes/logos.png">

## Introducción

Este proyecto se presentará en la actividad [Café con](https://humanidadesdigitaleshispanicas.es/cafe-con-gustavo-candela-4-de-abril-de-2023/) a modo de ejemplo del trabajo realizado sobre [colecciones como datos](https://collectionsasdata.github.io/) en el proyecto [BVMC Labs](https://data.cervantesvirtual.com) de la [Biblioteca Virtual Miguel de Cervantes](https://www.cervantesvirtual.com).

## Datos abiertos y enlazados

La Biblioteca Virtual Miguel de Cervantes publicó su catálogo de metadatos como [datos abiertos y enlazados](https://data.cervantesvirtual.com/datos-enlazados) (en inglés, Linked Open Data) utilizando como vocabulario principal [Resource, Description and Access](http://www.rdaregistry.info/). El repositorio se ha enriquecido con [Wikidata](https://www.wikidata.org) a través de diferentes propiedades creadas con el objetivo de enlazar [autores](https://www.wikidata.org/wiki/Property:P2799) y [obras](https://www.wikidata.org/wiki/Property:P3976).

Gracias al enriquecimiento, existe la posibilidad de explorar nuevas formas de acceso al catálogo por medio de nuevas propiedades proporcionadas por Wikidata (p. ej. nacionalidad o movimiento del autor) o visualizaciones basadas en el uso de gráficas y mapas.

<img src="imagenes/buscador.png" width="60%">

## Representación de las nacionalidades de los autores
El siguiente ejemplo muestra las nacionalidades de los autores de Wikidata enlazados a la Biblioteca Virtual Miguel de Cervantes. El siguiente [enlace](https://w.wiki/6WRC) permite ejecutar la siguiente sentencia SPARQL en el editor de consultas de Wikidata.

```
#defaultView:Map
SELECT DISTINCT ?autor ?autorLabel (SAMPLE(?imagen) as ?img) (SAMPLE(?coordenadas) as ?co)
WHERE {   
       ?autor wdt:P2799 ?idbvmc.
       ?autor wdt:P27 ?pais .
       OPTIONAL {?pais wdt:P625 ?coordenadas.}
       OPTIONAL {?autor wdt:P18 ?imagen .}      
    SERVICE wikibase:label { bd:serviceParam wikibase:language "es" }
} GROUP BY ?autor ?autorLabel
```

<img src="imagenes/mapa-autores.png">

## Información adicional

- [BVMC Labs](https://data.cervantesvirtual.com)
- [Collections as Data](https://collectionsasdata.github.io/)
- [International GLAM Labs Community](https://glamlabs.io/)
- [Impact Centre of Competence](https://www.digitisation.eu/)
- [GLAM Workbench](https://glam-workbench.net/)
- Migration of a library catalogue into RDA linked open data. Semantic Web 9(4): 481-491 (2018). https://doi.org/10.3233/SW-170274
- Gustavo Candela. Towards a semantic approach in GLAM Labs: the case of the Data Foundry at the National Library of Scotland. CoRR abs/2301.11182. https://doi.org/10.48550/arXiv.2301.11182


## Licencia y términos de uso

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Licencia Creative Commons" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/80x15.png" /></a><br />Esta obra está bajo una <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Licencia Creative Commons Atribución 4.0 Internacional</a>.

