# Similarity-based Iterative Feature Adder
Uses non-linear distance metric on iteratively stacked feature vector


# Supervised 

Type 1 -> supervised vertically stacked target distance
* Distance: Distance correlation by default
* Vertically stack to vector if distance to target vector decreases
* Keep track of correlations, ignore high correlation based on threshold, use cosine similarity by default
* Keep track of distance decrease per feature
* Sample M elements (optional, default is 100000)
* Require a priori normalisation, use quantile normalisation by default
--> stack feature vector/target vector iteratively

Type 2 -> supervised horizontally stacked target distance
* Global distance: Distance correlation by default, if not global has to be constructed as aggregation of local distances 
* Horizontally stack to feature matrix if distance to target vector decreases
* Keep track of correlations, for patient sub-typing, use cosine similarity by default
* Keep track of distance decrease per feature

Type 3 -> supervised inter-sample distance
* Partial Silhouette score between target groups based on fractional distance norms (settable, default 0.1, 0.5, 1, 2): use sampling for intra and mean/median for inter
* add dimension if partial silhouette score is increased
* Keep track of score increase per dimension

Sources:
* high dimensional distance: [1](https://bib.dbvis.de/uploadedFiles/155.pdf)
