# Relations in the Gene Ontology

## Overview
The following page documents the relations used in the filtered GO ontology. For information on how relations are represented in OBO format, see the OBO File Format Guide.
Understanding relations in GO
The ontologies of GO are structured as a graph, with terms as nodes in the graph and the relations (also know as object properties) between the terms as edges. Just as each term is defined, so the relations between GO terms are also categorized and defined. This document provides a description of some of the commonly used relationships in GO: is a (is a subtype of); part of; has part; regulates, negatively regulates and positively regulates.

This set is not exhaustive and includes only a subset of relations used in the GO ontologies, logical definitions and annotations. For more technical information about relations and their properties used in GO and other ontologies see the OBO Relations Ontology (RO) and for relationships used in GO annotation extensions, see the GO annotation extension relations file (experimental).

## Using relations to group related annotations

Relations are widely used by GO browsing tools such as AmiGO and QuickGO and in over-representation analysis to group related GO annotations. For example the annotations on the AmiGO page for kinase activity includes annotations made to 'tyrosine kinase activity', 'protein kinase activity' etc. Note that not all relations can be safely used to group annotations via the GO graph. Please see below for notes and examples illustrating when and why grouping of annotations via relationships can be done safely.

## Conventions used in the documentation
There are a number of ways of referring to and representing logical relations. The GO relations documentation uses the following conventions:

    in keeping with the graph-based terminology, node is used to refer to GO terms
    where it is appropriate to talk about a parent-child relationship between nodes, parent refers to the node closer to the root(s) of the graph, and child to that closer to the leaf nodes; for the relations is_a and part_of the parent would be a broader GO term, and the child would be a more specific term;
    the arrowhead indicates the direction of the relationship;
    dotted lines represent an inferred relationship, i.e. one that has not been expressly stated.

This diagram would be interpreted as follows:

diag-graph-example.gif

    A is a B
    B is part of C
    we can infer that A is part of C

The formal mathematical / logical representation of the inference made in the graph above would be:

is a ∘part of → part of
GO Basics
Nodes in the GO graph can have any number and type of relationships to other nodes. Like hierarchies—for example, a family tree or a taxonomy of species—a node may have connections to more than one child (more specific) node, but unlike them, it can also have more than one parent (broader) node, and different relations to its different parents; for example, a node may have a part of relationship to one node, and an is a relationship to another. The following diagram illustrates this point:

diag-dag-example.gif

    mitochondrion has two parents: it is an organelle and it is part of the cytoplasm;
    organelle has two children: mitochondrion is an organelle, and organelle membrane is part of organelle

The is a relation
The is a relation forms the basic structure of GO. If we say A is a B, we mean that node A is a subtype of node B. For example, mitotic cell cycle is a cell cycle, or lyase activity is a catalytic activity.

It should be noted that is a does not mean ‘is an instance of’. An ‘instance’, ontologically speaking, is a specific example of something; e.g. a cat is a mammal, but Garfield is an instance of a cat, rather than a subtype of cat. GO, like most ontologies, does not use instances, and the terms in GO represent a class of entities or phenomena, rather than specific manifestations thereof. However, if we know that cat is a mammal, we can say that every instance of cat is a mammal. 
