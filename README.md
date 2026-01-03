# NBA Knowledge Graph Project

**Course**: Bases de Données Spécialisées – Master 2 MIADS  
**University**: Université Paris Cité  
**Academic Year**: 2025-2026  
**Authors**: Chris ESSOMBA, Ivan BANFOU

## Overview

This project implements a **knowledge graph** focused on the **NBA** (players, teams, and games) as part of the "Knowledge Graphs et Raisonnement" assignment.

The goal is to demonstrate the full pipeline:

- Extraction and integration of heterogeneous open datasets
- Conversion to RDF
- Advanced SPARQL querying
- RDFS reasoning with inference

## Datasets

Two public datasets from Kaggle were used:

1. **NBA Games** – Nathan Lugan  
   Link: https://www.kaggle.com/datasets/nathanlauga/nba-games  
   Contains match details (date, teams, scores, season, etc.).

2. **NBA Players & Teams** – Wyatt Walsh  
   Link: https://www.kaggle.com/datasets/wyattowalsh/basketball  
   Contains player information and current team assignments.

Common concept: **team_id** → used for integration.

## Project Structure

.

```
├── data/
│   ├── games.csv
│   └── players.csv
├── turtles_files/
│   ├── nba_graph.ttl                # Integrated RDF data
│   └── schema_rdfs_complet.ttl      # RDFS ontology
├── notebook.ipynb                   # Complete workflow (extraction, RDF generation, queries, reasoning)
└── README.md                        # This file
```

## Key Features

- **RDF Modeling**: Unique URIs for players, teams, and games. Links via `playsFor`, `homeTeam`, `visitorTeam`.
- **RDFS Schema**: Hierarchical classes (`Player ⊑ Person`, `Team ⊑ Organization`, `Game ⊑ Event`) and properties (`involvesTeam`, `hasName`, `hasPoints`) with subPropertyOf, domain/range.
- **10 SPARQL Queries**: Including federation (DBpedia), OPTIONAL, named graphs, aggregation, property paths, MINUS/FILTER NOT EXISTS.
- **RDFS Reasoning**: Using `owlrl` to show inferences (subClassOf, subPropertyOf, domain/range).

## How to Run

1. Install dependencies:

```bash
pip install pandas rdflib owlrl
```
