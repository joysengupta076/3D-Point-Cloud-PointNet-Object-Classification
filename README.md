# 3D-Point-Cloud-PointNet-Object-Classification
This project involved training the PointNet Neural network architecture for predicting the classification of object from 3D Point Clouds. 

## Model description
The PointNet model has been used for classification. PointNet architecture has the advantage of being able to work with less voluminious modes of data directly from point cloud information as opposed to flattening of using 3d voxels in other models. The PointNet model involves pose normalization as point clouds can consist of object data in various poses which should be detected. This is done by spatial transformations in a T-net subnetwork by a series of matrix multiplications.

A higher dimensional global feature vector is formed from the input to the output layers which, along with local point features, is directly used for classification. The local point features are used for segmentation. The global feature vector is formed from a set of points which define the object features since they pass through the max pooling layer, hence all lesser values have been neglected. And as long as they are lesser than the max value, they will not contribute to the global feature vector and hence will not play a role in defining the object.

Finally densely connected layers convert the global feature vector into probabilities of each class through softmax.

As for the input point cloud, a significant portion of the project has been in artificially synthesizing point cloud to simulate LiDAR point clouds.
3D object mesh dataset was downloaded from "http://3dvision.princeton.edu/projects/2014/3DShapeNets/ModelNet10.zip".
Sampling of the 3D objects by, for instance 2048 samples and having a 3D subplot by scatter means gives us a close point cloud synthesis of the objects. For the requirement of training and predicting, since the dataset is the same the discrepancy in the number of samples per object does not matter here as compared to a real life LiDAR point cloud data. However, in the latter part of code sections noise has been added to better simulate one.

The code is derived from the Point Cloud project by https://github.com/niconielsen32.

### References:
https://github.com/niconielsen32/NeuralNetworks/blob/main/PointCloudPointNet.ipynb

https://medium.com/@luis_gonzales/an-in-depth-look-at-pointnet-111d7efdaa1a

https://doi.org/10.48550/arXiv.1612.00593

