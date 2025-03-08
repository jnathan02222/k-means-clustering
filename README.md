# K-Means Clustering Library

This is a simple K-Means clustering library written in JavaScript. It includes an implementation of the K-Means++ initialization algorithm and silhouette scoring to determine the best number of clusters.



## Features

- K-Means clustering with K-Means++ initialization
- Silhouette scoring to optimize the number of clusters



## Installation

```bash
npm install k-means-clustering
```



## Usage

### 1. K-Means Clustering

Use `kMeans` to cluster vectors into `k` groups:

```js
const { kMeans } = require('k-means-clustering');

const vectors = [
  [1, 2],
  [3, 4],
  [5, 6],
  [8, 9],
  [10, 11]
];

const k = 2;
const { centroids, clusters } = kMeans(vectors, k);

console.log('Centroids:', centroids);
console.log('Clusters:', clusters);
```



### 2. Find Best K Using Silhouette Score

Use `manyKMeansWithSilhouette` to test different values of `k` and pick the one with the highest silhouette score:

```js
const { manyKMeansWithSilhouette } = require('k-means-clustering');

const bestResult = manyKMeansWithSilhouette(vectors, 2, 5);

console.log('Best Centroids:', bestResult.centroids);
console.log('Best Clusters:', bestResult.clusters);
```



### 3. Utility Functions

- `calculateCentroid(cluster)` – Computes the centroid of a cluster.
- `initalizeKMeans(vectors, k)` – Initializes centroids using K-Means++ method.



## Error Handling

Currently error handling has not been implemented.

Please ensure that vectors are of the same dimension (not 0).
k should be a valid value for the number of vectors 

## Example

Sample input and output:

```js
const vectors = [
  [1, 2],
  [3, 4],
  [5, 6],
  [8, 9],
  [10, 11]
];

const k = 2;
const result = kMeans(vectors, k);

console.log(result.centroids); // [[4, 5], [9, 10]]
console.log(result.clusters); // [[[1, 2], [3, 4], [5, 6]], [[8, 9], [10, 11]]]
```



## License

This project is licensed under the MIT License.

