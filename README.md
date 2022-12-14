# Field Boundary Mapping in Small Scale Farming using Multi-Resolution Satellite Data
## _A Case Study in Cambodia and Viet Nam_

##
|Authors|Xinyan Fan, Claudia Paris, and Claudio Persello|
|---|---|
|Contacts |x.fan-1@utwente.nl|
|Version|0.1 |

## Project Overview
The monitoring and mapping of agricultural fields via satellite imagery are crucial to sustainable agricultural management, especially for developing countries. The project is aimed at developing automatic workflows for mapping rice field boundaries in small-scale farming, using advanced image processing and deep learning neural networks.
The workflow has been developed in the context of the project "Developing a spatially-explicit agricultural database in support of agricultural planning", supported by the Ministry of Agriculture, Forestry and Fisheries (MAFF) of Japan and implemented by the Statistics Division of the Food and Agriculture Organization (FAO) of the United Nations.

## The workflow
The workflow consists of the following steps:
- Pre-training the U-Net model on publicly available datasets
- Fine-tuning the U-Net on a small local training dataset
- Applying watershed transform to obtain closed segments
- Producing the geodatabase of crop polygons and evaluating performance by computing PoLiS distance metric

The implementation of the workflow is split into the following three Jupyter notebooks and set up to run on various cloud platforms such as [Google Colab](https://colab.research.google.com/) and the Geospatial Computing Platform [CRIB](https://crib.utwente.nl/) of the University of Twente.

- ***network-training.ipynb*** trains a network with a given configuration
- ***network-testing.ipynb*** includes the accuracy assessment as well as the sample outputs from the training dataset
- ***network-prediction.ipynb*** predicts the field boundaries (stored as TIF images with geolocations) using a pretrained network.


It should be noted that the code is extended from the results of a student assignment in one of the minors at the University of Twente. We thank the following students for their contribution to the original version of the code.

* Floor Stefess
* Lars van der Velde
* Laurens Laarhuis
* Matthijs Horst
* Max Resing
* Paula Janeka
* Simonas Bud??jis


## Case studies

The automatic boundary delineation is carried out for rice fields in Cambodia and Viet Nam, where rice paddy occupies a large portion of the agricultural area. The obtained geospatial database of rice farms will be used to increase the availability and quality of farmland information to:

- definition of effective schemes of farming incentives,
- support the formulation of smart agriculture programs, and
- improve reporting on Sustainable Development Goal (SDG) 2.4.1 for sustainable agriculture. 

A tailored workflow should be developed in order to address two main challenges: (1) the lack of high-quality reference (label) data, and (2) the fragmented agricultural areas characterized by very small fields (i.e., less than 1 ha). 

## Data set

All the data sets are available online. They include:
- Multi-resolution earth observation data: [Sentinel-2 and PlanetScope](https://surfdrive.surf.nl/files/index.php/s/Euh88Cl15jRbq7Y) 
- Reference data: 
    1. [Publicly available](https://easy.dans.knaw.nl/ui/datasets/id/easy-dataset:200357) crop boundaries dataset of approximately 1 million fields in the Netherlands for pre-training the network on Sentinel-2 images.
    2. [Local training data set](https://surfdrive.surf.nl/files/index.php/s/Euh88Cl15jRbq7Y) of 3800 fields in Viet Nam generated by photo-interpretation from Worldview 2.  

## Acknowledgment

We use the Python implementation of the PoLiS metric (see the original code on https://github.com/spgriffin/polis)

## License
The code is published under the [GPL-3.0 license](https://www.gnu.org/licenses/gpl-3.0.en.html). Details can be found in the LICENSE file.
