# Word Dependencies

Parse dictionary to build dependency graph of words in a language to discover
the minimal set of words needed to describe all other words in the language.

## Methodology

```
For each word (_w_) create a node in the graph _G_.
For each definition of word (_w_)
	For each subword (_v_) in the definition of _w_
		Create an edge from _w_ to _v
```

Search the graph for all node that only have edges leaving them (or have no 
edges going in).
* This set of words, if it exists, is enough to rebuild the language of meaning.
* If it does not exist, find the set of words that is
    * cyclic OR
    * is the subset of nodes that when treated as a whole satisfies (I).
