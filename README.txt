A novel Feature Selection Strategy Based on Salp Swarm Algorithm  for Diseased Plant Classification

Dataset

Data 		Description
Arrhythmia 	16 groups,279 attributes,452 instances
CNAE-9		9 groups,857 attributes,1080 instances
Heart 	                2 groups,13 attributes,303 instances
Urban Land Cover 	9 groups,148 attributes,168 instances	
apple                       3 groups,171 attributes,750 instances(scab,black rot, cedar apple rust)
corn                         3 groups,171 attributes,1200 instances(gray leaf spot, rust, northern leaf blight)
coffee                      3 groups,171 attributes,1453 instances(leaf miner, phoma, and rust)
grape                       3 groups,171 attributes,2400 instances(black rot, black measles, leaf blight)
corn rust                  3 groups,171 attributes,1200 instances(rust early, mid, and late stages)
coffee miner            3 groups,171 attributes,321 instances(rust early, mid, and late stages)

    
Environment and Tools

Keras 2.2 & Tensorflow 1.13.1 GPU
numpy 1.14.0
opencv-python 4.2.0.34
pandas 0.25.3
scikit-learn 0.22.2

IDE Used

jupyter notebook

Code

1.
    background_removal
    The background removal module enables the removal of the background and keep only the valid area of the plant leaves.
	source_path = "input/"  
	save_path = "output/"  
2.
    feature extraction
    The feature extraction module implements the following functions: from each image, the colour features of the image are obtained using the colour moments ，the texture features of the image are obtained using the grey scale co-occurrence matrix and local binary patterns. 
	input:plant disease image
	output:feature vector.
3.
    neural network classifier
    The neural network classifier module performs the following functions: it takes a subset of optimal features as input to the classifier and tests the classification performance of the optimal features. 
    It includes an input layer, two hidden layers , and an output layer .	
	adjustable parameters:the number of neurons in the hidden layer and the number of categories in the output layer can both be adjusted.
	input：optimal feature subset of each dataset(file is of type csv)
	output:plots and values of accuracy and loss
4.
    SSAFS
    An improved salp swarm algorithm for feature selection, which is used to optimize the feature subsets from all the color and texture features. 
    It contains population initialisation, fitness calculation and ranking, leader and follower position updating and feature subset quality assessment.
	adjustable parameters:number of initialized populations, balancing parameter r1 for exploration and exploitation, total number of iterations, parameters in the fitness function
	input:features of plant disease images(file is of type csv)
	output:best fitness, number of feature subsets, feature subsets and average classification accuracy of KNN five-fold cross-validation.