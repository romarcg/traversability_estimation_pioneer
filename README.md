# Complementary material for the submission 224 to CoRL 2017

> **All the supplemented material is presented anonymously**


> This is the **[version of the document submission](submission/submission_224.pdf)** with **high-quality figures**.

This repository provides: 
1. media material of the experiments on the real robot and real elevation maps ([media](#media)),
2. heightmaps and csv files to generate the training and evaluation datasets ([data](#mata)), 
3. and the source code to each module of our traversability estimation framework ([code](#code)):
   * simulation and data generation,
   * heigthmaps generation, 
   * datasets generation, 
   * definition and training of the CNN classifier,
   * evaluation of the trained network, 
   * and visualization of the results as traversability maps and 3D renderings 
   > verify the [software requirements](#software-requirements) to test the code

## Media

This is a selection of the available media of our traversability estimation framework: 

**video demonstration of the experiments on the real robot**


**animation of the traversability maps for the quarry dataset (32 orientations)**

**animation of the minimal traversability map for the quarry dataset**

**high-quality images of the evaluation heightmaps (surfaces) and of the experiments on real robots**


> A larger number of visualizations can be generated/found in the `code`>`visualization` section of this repository.

## Data

This folder contains the heightmaps (grayscale images) and the csv files with the data from each simulated trajectory


## Code

In this folder we provide several subfolder for each module of our traversability estimation framework:

### simulation

Code for simulating the Pioneer 3AT robot on a generated heightmap. 

This code can be accessed as a docker image that setups all the needed libraries:

> [link to docker image](link)

Or by copying the `simulation` folder files to an existing ros+gazebo setup.

### heigthmap generation

This folder contains a document explaining in detail the procedural generation of heightmaps and a script that implements such procedure.

### dataset generation

This script takes a csv file and builds a `dataframe` that is used to generate the training/evaluation/real-evaluation dataset.

### training

This script builds the CNN architecture, takes the dataset generated by the previous script and starts the network training (this task may take several hours).

The model generated by this script is saved to be used in future scripts.

> An already trained model file is provided to avoid the training step.

### evaluation

This script calculates evaluation stats for the trained model using the evaluation datasets.

### visualization

This script generates (for a given testing heightmap) traversability maps in many orientations. Also, an additional 3D rendering is performed to interactively examine the heightmap and the traversability map.

> A set of already generated traversability maps is provided as sample files to avoid regenerating them.


### Software requirements

In order to use the provided scripts, these are the list of requirements:

  * python 3.5.3
  * numpy 1.12.1
  * matplotlib 2.0.0
  * pandas 0.19.2
  * tensorflow-gpu 1.0
  * keras 2.0.3
  * scikit-learn 0.18.1
  * scikit-image 0.13.0
  * joblib 0.11
  * mayavi
