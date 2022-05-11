# Table of Content
1. [ Abstract ](#desc)
2. [ Data ](#usage)
  * [ organism_to_effector module ](#mod1)
  * [ effector_to_organism module ](#mod2)
  * [ organism_to_reactants module ](#mod3)
3. [ Additional Files ](#examp)


<a name="desc"></a>
## 1. Abstract

The hierarchical ontology of the KinMod database allows flexible exploration of data attributes and investigation of metabolic relationships within- and cross-species. Representing missing experimental values supports the rational experimental design to abridge kinetic parameter measurements. Linking multi-omics data and providing data on the metabolic regulation network encourages the development of novel machine learning techniques for predicting missing kinetic parameters and promotes accurate kinetic model construction of cells metabolism by providing a comprehensive list of available kinetic measurements. To define a thorough depiction of KinMod data, we develop six analyses to visualize associations between data classes belonging to separate sections of the metabolism. Through these analyses, we demonstrate that the KinMod database provides a unique framework for biologists and engineers to retrieve, evaluate and compare the functional metabolism of species, including the regulatory network, and discover the extent of available and missing experimental values of the metabolic regulation. 

<a name="usage"></a>
## 2. Data

To allow a comprehensive analysis of the data, we developed three analysis modules in the KinMod web application. The organism_to_effector module allows flexible exploration of linked effector molecules and available KI parameters to a specific organism, providing the opportunity of investigating the regulatory networks within species. The effector_to_organism module enables the investigation of the regulation effect of a given molecule across species, providing the opportunity to compare the functional metabolism of organisms. the organism_to_reactants module allows exploration of available KM parameters in a given organism, opening up insights into the saturation of enzymes within species. 

<a name="mod1"></a>
  * **organism_to_effector module:** 

This module lists available regulatory interactions observed in an organism of interest, such as Escherichia coli. 

> **organism_to_effector('*Escherichia coli*')**  
  
> 5305 row(s) returned 
> Duration: 25.828 sec / 0.359 sec 


The resulting table lists organism name, enzyme EC Number, effector IUPAC name, effector IID, effector SMILES, Effector InCHIKEY, KEGG ID, Inhibitor tag, Activator Tag, KI parameter(s), and additional comments.  
Effector IID is the internal KinMod identifier assigned to distinct chemical molecules based on their first layer of InCHI string. The inhibitor tag is one for inhibitor molecules, and for activator molecules, the activator tag is one. Additional comments can include a range of reported kinetic parameters, the experimental conditions or reveal if the enzyme was induced in the organism.  
  
<a name="mod2"></a>
  * ** The effector_to_organism: **

module outputs all observed regulatory interactions across species of a molecule of interest.  

> **call LMSE.effector_to_organism('citrate');** 
> 401 row(s) returned 
> 1.609 sec / 0.000 sec 
  
This module returns the organism names and EC numbers for which citrate act as an effector. Also, the structure of this molecule, inhibitor tag and activator tag can be obtained.  
<a name="mod3"></a>
* **The organism_to_reactant module:**

> **call LMSE.organism_to_reactant('*Escherichia coli*')**
> 3112 row(s) returned 
> 2.500 sec / 4.375 sec 
  
This module returns the KM values reported for EC numbers in Escherichia coli. The output table includes information on the reaction string, the EC number, reactants IUPAC name, and KM values. 


***
<a name="examp"></a>
## 3. Additional Files