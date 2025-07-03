# Multiplex Immunophenotyping Classification in Breast Tumor

Top: Representative mQIF of the tumor microenvironment of a breast cancer TMA core, stained for cell nuclei (DAPI, blue); CD8 (FITC, green); PDL-1 (Cy5, red); CD68 (TRITC, carmine); pan-cytokeratin (Cy7, cyan). Points (coordinate map) extracted using a commercial software package HALO where x and y-coordinates represents the physical cell location and z-coordinate represents the immunophenotype. Point cloud data used for the deep learning analysis in tiled-based processing. Bottom (1,2): The point cloud saliency map based deep learning strategy takes N points from the mQIF TMAs slides per tile. The data passes through feature extraction layers, a max pooling layer, classification layers and saliency maps construction. The feature extraction is comprised of five dense layers with 64, 64, 64, 128, and 1024 neurons, respectively, that share weights across each point. The max pooling layer applies a symmetric function reducing the features to 1024 × 1 dimensions. The output of the max pooling layer is fed to two fully connected layers with 512 and 256 neurons, respectively, which is fed to a dropout layer and finally a softmax layer for classification. Saliency maps are then constructed to detect the key phenotypes of the DNN model by calculating gradients, which guide point-dropping in an iterative process as follows: compute the gradient, compute the spherical core, compute distance to the spherical core, construct the saliency score map, dropping points.

<img width="672" alt="image" src="https://github.com/user-attachments/assets/4a06a653-7895-4e25-a087-1ff15a9edb54" />





Breast cancer is the leading cause of cancer death in women where non-hispance Black (NHB) patients continue to have 41% higher death rates compared to non-hispanic White (NHW) patients. Here, we provide clinical data analysis using point cloud saliency map based deep neural network (DNN) strategy. We classify and characterize race-associated differences from single cell multiplex quantitative immune-fluorescence tissue microarrays from unique cohort of race diverse 555 NHB and NHW breast cancer patients. The DNN model achieved significant overall validation accuracy of 0.903 (95% CI 0.907-0.899) as well as accuracy of 0.905 (95% CI 0.912-0.899) and 0.901 (95% CI 0.909-0.893) for NHB and NHW breast cancers respectively. The key differential phenotypes of the DNN were characterized into understandable descriptions of the patterns that enabled successful predictions. We show the complex architectural interplay between tumor cells and surrounding immune and stromal components that makes the regulatory distinction between NHB and NHW breast tumors. Our results indicates that NHB tumors may have different and more complex breast tumor microenvironment milieus than NHW tumors.


![image](https://github.com/user-attachments/assets/533f82d4-c7ff-4cfb-a9b4-957e5ac921d9)

Classification performance of DNN for single cell multiplex immunophenotyping with point clouds retrieved from 555 NHB and NHW breast tumors. A. Performance of validation accuracy for different tile sizes. B. Performance of validation for the selected tile size. C. Training and validation progress curves for every 300 epochs.

![image](https://github.com/user-attachments/assets/6fe3fc58-4fd3-4079-a7f0-0f7c1a489dcb)

The constructed point-cloud saliency maps of the validated NHB and NHW DNN were analyzed to characterize the distribution of the critical single cell phenotypes. Left: Probability ratio of presence of a single critical phenotype in NHB vs. NHW breast tumors as detected from the saliency maps. Right: Saliency maps analysis for the probability ratio of co-presence of two different critical phenotypes in NHB vs. NHW breast tumors. 




References:
1.	Charles R. Qi, H. S., Kaichun Mo, Leonidas J. Guibas. PointNet: Deep Learning on Point Sets for 3D Classification and Segmentation. Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition, 652-660 (2017).
2.	Tianhang Zheng, C. C., Junsong Yuan, Bo Li, Kui Ren. PointCloud Saliency Maps. Proceedings of the IEEE/CVF International Conference on Computer Vision, 1598-1606 (2019).
