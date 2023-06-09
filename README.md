# Identifying_gamma_hadron_magic_dataset


This data set is taken from Kaggle (https://www.kaggle.com/datasets/abhinand05/magic-gamma-telescope-dataset)

## About the data : 
MAGIC gamma telescope data 2004
Dataset Information.
The data are MC generated (see below) to simulate registration of high energy
gamma particles in a ground-based atmospheric Cherenkov gamma telescope using the
imaging technique. Cherenkov gamma telescope observes high energy gamma rays,
taking advantage of the radiation emitted by charged particles produced
inside the electromagnetic showers initiated by the gammas, and developing in the
atmosphere. This Cherenkov radiation (of visible to UV wavelengths) leaks
through the atmosphere and gets recorded in the detector, allowing reconstruction
of the shower parameters. The available information consists of pulses left by
the incoming Cherenkov photons on the photomultiplier tubes, arranged in a
plane, the camera. Depending on the energy of the primary gamma, a total of
few hundreds to some 10000 Cherenkov photons get collected, in patterns
(called the shower image), allowing to discriminate statistically those
caused by primary gammas (signal) from the images of hadronic showers
initiated by cosmic rays in the upper atmosphere (background).

Typically, the image of a shower after some pre-processing is an elongated
cluster. Its long axis is oriented towards the camera center if the shower axis
is parallel to the telescope's optical axis, i.e. if the telescope axis is
directed towards a point source. A principal component analysis is performed
in the camera plane, which results in a correlation axis and defines an ellipse.
If the depositions were distributed as a bivariate Gaussian, this would be
an equidensity ellipse. The characteristic parameters of this ellipse
(often called Hillas parameters) are among the image parameters that can be
used for discrimination. The energy depositions are typically asymmetric
along the major axis, and this asymmetry can also be used in discrimination.
There are, in addition, further discriminating characteristics, like the
extent of the cluster in the image plane, or the total sum of depositions.

The data set was generated by a Monte Carlo program, Corsika, described in
D. Heck et al., CORSIKA, A Monte Carlo code to simulate extensive air showers,
Forschungszentrum Karlsruhe FZKA 6019 (1998).
The program was run with parameters allowing to observe events with energies down
to below 50 GeV.


## About this project :
In this project, the main aim was to identify gamma in a haystack of hadrons. The dataset contains more gamma data than hadron data. Looking at the pairplot we performed the classification task using the Ensemble techniques. Looking at the ROC curve, AUC score and PR curve we can say that RandomForest Classifier did the best job. The hyperparameter tuning was also performed but the result did not improve much. As there were a difference in number of hadron and gamma data, the upsampling technique was also perfomed using RandomOverSampler and SmotekTomek. The AUC scores have not improve much from the initial one, though if we take a look at the precision-recall values, SMOTETomek has the best one. 

Next we also performed the threshold tuning technique to improve predictions. As \nthe metric for SMOTETomek is the best among all the models discussed, we decided to perform the threshold tuning for this model. We obtained the optimum threshold for this case and using this threshold value we obtain predictions. This time the metrics and the confusion matrix we get is better than what we had earlier. 
