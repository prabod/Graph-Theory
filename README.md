# Graph-Theory-Ford-Fulkerson [![Build Status](https://api.travis-ci.org/prabod/Graph-Theory-Ford-Fulkerson-Maximum-Flow.svg)](https://travis-ci.org/prabod/Graph-Theory-Ford-Fulkerson-Maximum-Flow) [![Dependency Status](https://david-dm.org/prabod/Graph-Theory-Ford-Fulkerson-Maximum-Flow.svg)](https://david-dm.org/prabod/Graph-Theory-Ford-Fulkerson-Maximum-Flow)


> Ford-Fulkerson Algorithm for Maximum Flow Problem

## Introduction

*A flow network is represented as a directed acyclic graph(DAG). Each edge has a maximum capacity, which the flow cannot exceed. The source node s has no incoming edges, and the sink node t has no outgoing edges. All other nodes are called internal nodes. we can find the maximum possible flow from s to t with following constraints:*

1. Flow on an edge doesn't exceed the given edge capacity
2. Incoming flow is equal to Outgoing flow for every internal vertex

## Algorithm

1. Start with f(e) = 0 for all edge e ∈ E.
2. Find an augmenting path P in the residual graph Gf .
3. Augment flow along path P.
4. Repeat until you get stuck.

## Example

*Consider the following graph*

<img src="/images/ford_fulkerson11.png">

*Maximum possible flow in the given graph is 23*

<img src="/images/ford_fulkerson2.png">

```javascript
var fordFulkerson = require('graph-theory-ford-fulkerson');

var graph = [
	[ 0, 16,  13, 0,  0,  0 ],
    [ 0,  0, 10, 12,  0,  0 ],
    [ 0,  4,  0,  0, 14,  0 ],
    [ 0,  0,  9,  0,  0, 20 ],
    [ 0,  0,  0,  7,  0,  4 ],
    [ 0,  0,  0,  0,  0,  0 ]
];

console.log("The maximum possible flow is " +
	fordFulkerson(graph, 0, 5));
```

## Usage

#### `require('graph-theory-ford-fulkerson')( graph, source, sink )`
Compute the maximum flow in a flow network between source node `source` and sink node `sink`.

**Arguments:**
- `graph`: The Graph which representing the flow network
- `source`: source vertex
- `sink`: sink vertex

**Returns:** Returns a number representing the maximum flow.

## Installation

	npm install graph-theory-ford-fulkerson

## License

&copy; 2016 Prabod Rathnayaka. MIT License.
