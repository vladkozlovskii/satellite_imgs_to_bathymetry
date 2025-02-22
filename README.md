# satellite_imgs_to_bathymetry
Here I tried to predict sea depth from satellite images and a small number of bathymetry data

I took Sentinell satellite image (6 channels) and bathymetry data (GEBCO) at depths of 0-15 meters. There are also data on coordinates and distance of points from shore (they are not used in the model). Bathymetry data are transferred to the satellite image grid.  
The size of the training sample depends on how many points from the satellite grid will be assigned depth values from the GEBCO grid. if the distance is too large (and more points will be assigned values from the gebko grid), the result will be less valid. in addition, if a sequential neural network is used, the model is well trained (and retrained) and the result looks unnatural (all training points are predicted by GEBCO grid values).  
Several models were tested (Random Forest, Light GBM, neural network), key metric MAPE.  
At the end a bathymetry map was prepared.
