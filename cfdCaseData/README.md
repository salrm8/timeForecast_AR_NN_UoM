# CFD use cases and data

## Folders
* `mixlay_nek5000`: 2D mixing layer use case in Nek5000

## Data

### Mixing layer
The snapshots, and the results of the POD are available on cloud (can be downloaded by permitted users).
List of files:

* `MASmixlay0.f00001`: Mass matrix of the CFD grid <br>
   Use: required for POD
* `Mixlay_3982_snapshots.tar`: original snapshots of the mixing layer: 1 to 3982 (all snapshots are equispaced in time) - tar format <br>
   Use: visualization or analysis (needs pymech)
* `mixlay_1to3982_velPickle`: velocity snapshots of the mixing layer 1 to 3982 (all snapshots are equispaced in time) reformatted as a database and saved in pickle. <br>
   Use: Can directly be used to do POD, DMD, etc. See `pod_mixlay.ipynb`
* `pod_mixlay_1to3982_velPickle_3000.npz`: 3000 POD modes of the mixing layer (eigenvalues, spatial modes, temporal coefficients). <br>
Use: Use `pod_postprocess.ipynb` for visualizing and post-processing these results. 


