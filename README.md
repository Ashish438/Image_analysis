# Image_analysis
The following python code does analysis of histopathological cancer whole slide images which are in a very high resolution .svs format. It involves image manipulation and extraction of nuclear and cellular for automated detection of cancer 

Details:

1.) Our input images are the histopathological images downloaded from TCGA database. These images are known as whole slide images and are in .svs format. They are very high resolution images  and therefore their size is significantly high and so these .svs images cannot be processed or viwed using the default image viwer present in our system.

2.)So the first step in our image analysis protocol is to split the large .svs image into many smaller low  resolution .png images known as tiles.This makes our image processing easier, as now instead on working on the whole .svs image (which would have been tedious) we would be doing our processing on each of the tiles that we have generated from our parent image.

3.)After succesfully splitting the .svs images we then need to perfrom certain fundamental image manipulating methods which are color normalisation, color deconvolution, nuclei segmentation.

4.)Color Normalisation: There might be some distortions in the image due to uneven lighting and normalisation helps us to get rid of such distortions as well as shadows. Our input for this step in the splitted png tile.

5.)Color Deconvolution:The input for this step is the normalised png tile. In this step we convert the RGB channels  of our image into Haemotoxylin(nuclear stain) and Eosin(cytoplasmic stain) channels because these two were the stains that were used to stain the tissue that is bieng shown in the image.

6.)Nuclei Segmentation:The input for this step is the color deconvoluted png image. In this step we identify and isolate  the nuclei that are present in our image. It is the most crucial step for efiicient feature extraction.

7.) After the nuclei segmentation step our next and the final step is the extraction of certain features from these png images and perform statistical operations on them.

8.)We extracted ten features for each cell in the split image. The seven types of morphological and spatila features of cell  nuclei were: major axis length(Major_Axis), minor axis length(Minor_Axis), the ratio of major to minor axis length(Ratio), nuclear area(Area), mean distance to neighbouring cells(Mean_Distance), maximum distance to neughbouring cells(Max_Distance), minimum distance to neughbouring cells(Min_distance) and the other three features were red, blue and green pixel trait at the centroid of each nuclei of each cell.

9.)After successfull extraction of all these ten features we performed certain statistical operations on each these features. The statistical operations were average, variance, standard deviation, skew, kurtosis and entropy. So in total we have ten features and each of the ten features have five statistical operations associated with them.

###The code also generates a GUI in which the user just have to add the path of the input folder which contains all the sub folders containing .svs whole slide images of cancer.
