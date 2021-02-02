# corrosion-detection-n-classifier

# Introduction 

Corrosion detection is task carried out in industries manually which can be expesive and faliure to identify this can cost huge amount of losses to life, resources and environment
But in recent years with the developement in computer visions techniques these taks can be easily automated. Presently for Non Destructive Testing (NDT) industries use radiography, ultrasonic, eddy current, magnetic particle etc , which are time consuming and expensive. So by use of computer vision techinques we speed up the regular maintainance process and also this technology can be extended to drones to reach places where humans can't reach. 

# Computational Model
A computational model is basically a mathematical model that can be used to simulate the physical properties of system. It takes into account physical, chemical ,etc properties of system to simulate the system.The simple idea behind the model was that corroded surface will have relative rough surfae and the colour would lie in particular range. There were many challanges which our model would have to overcome like roughness can be both due corrosion and irregularities in paint coat or dust atc and same colored pixel could have belonged to both corrosion and non-corrosion region.
So the math behind the model is based on Francisco Bonnin-Pascual and Alberto Ortiz.

The first stage of the model is based on the premise that a corroded area presents a rough texture. Roughness is then related to the energy of the symmetric gray-level co-occurrence-matrix (GLCM), calculated for downsampled intensity values between 0 and 31, for a given direction α and distance d . The energy is obtained by means of Equation 1:


where p(i, j) is the probability of the occurrence of gray levels i and j at distance d and orientations α or α + π. Patches with an energy lower than a given threshold τE, i.e. exhibit a rough texture, are finally candidates to be more deeply inspected.
The second stage filters the pixels of the patches that have passed the roughness stage. This stage makes use of the colour information that can be observed from corroded areas. More precisely, the classifier works over the Hue-Saturation-Value (HSV) space after the realization that HSV-values that can be observed in corroded areas are confined in a bounded subspace of the HS plane. Although the V component has been observed neither significant nor necessary to describe the color of corrosion, it is used to prevent the well-known instabilities in the computation of hue and saturation when color is close to white or black. In that case, the pixel is classified as non-corroded.
A training step is performed prior to the application of this second stage of the corrosion classifier. In this case, training consists of building a bi-dimensional histogram of HS values for image pixels known to be affected by corrosion in the training image set. The resulting histogram is subsequently filtered by zeroing entries whose value is below 10% the highest peak.
The classifier proceeds as follows for every 3-tuple (h,s, v):
1) pixels close to black, v < mV, or white, v > MV ∧ s < mS, are labeled as non-corroded,
and
2) for the remaining pixels, the HS histogram is consulted and the pixel is labelled as corroded if 
HS(h,s) > 0,
for given thresholds mV, MV and mS.
Notice that the stages of the algorithm cannot be reversed since they do not work with the same kind of entities: while the second stage works at the pixel level, the first stage operates over 15 × 15 -pixel image patches since it depends on texture, which necessarily involves a pixel neighborhood. Figure 1 shows the flow diagram of WCCD.
Working code for this model is under process and testing. Other algorithm like edge detection is also being tried to incorporate in order to improve performance.

# Convolutional Neural Network




# __
it is an ongoing project and all work and code will be uploaded soon.
A working demo of this application hosted on the github page where all techinalities will also be explaned .

Star this repo to learn about the new developements .
Thanks for visiting.
