**Characteristics**
- Is a type of instance-based learning or non-generalizing learning
- Simply stores instances of the training data
- Classification is computed from a simple majority vote of the nearest neighbors of each point 

**scikit-learn implements two different nearest neighbors classifiers**
- KNeighborsClassifier
	- learning bases on the k nearest neighbors of each query point
- RadiusNeighborsClassifier
	- Implements learning based on the number of neighbors within a fixed radius r of each training point
	- For high-dimensional parameter spaces, this method becomes less effective due to the so-called ''curse of dimensionality''
**Algorithms**
- Brute Force 
	- The implementation involves the brute-force computation of distance between all pairs of points in the dataset, for N samples in D dimensions
	- With a complexity of $\mathcal{O}(D \times N^2)$
	- In scikit-learn are specified using the keyword ```algorithm = 'brute' ```
- K-D Tree
	- The computational cost of a nearest neighbors search can be reduced to $\mathcal{O}(DN \log (N))$ or better
	- Though the KD tree approach is very fast for low-dimensional $(D < 20)$ neighbors searches
	- n scikit-learn are specified using the keyword ```algorithm = 'kd_tree' ```
- Ball Tree
	- The computational cost of a nearest neighbors search can be reduced to $\mathcal{O}(D \log (N))$ or better, but this algorithm is more costly that K-D Tree
	- n scikit-learn are specified using the keyword ```algorithm = 'kd_tree' ```
	