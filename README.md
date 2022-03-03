# Electroencephalograph (EEG) Visualization

## Project Motivation 
This project was part of the required coursework for The University of Texas at Austin's Elements of Data Visualization course. The goal of this project is to analyze and visualize data related to our respective major, that being neuroscience in my case. 

## Code
**Language**: Python, HTML, CSS <br>
**Packages**: altair, matplotlib, mne, numpy, scipy, sklearn

## Data 
This dataset was obtained from The University of Texas at Austin's Neuroscience Data Analysis in Python course. The dataset contained time series, millivolt, and channel name data within a MATLAB (.mat) file. All 64 channels had 99 trials with 640 time points each, which amounted to over four million data points overall. Due to a large amount of data, the trials were averaged into one trial which reduced the dataset to 40,960 data points. 

### Data Transformation / Clustering
To prepare the data for the final visualization, the following changes were implemented: 
- Dimensionality reduction using Principal Component Analysis (PCA) 
- Gaussian Mixture Model clustering 
- Wide-form to long-form data transformation 
- Create cluster classification column

## File Descriptions
`eeg-alpha.ipynb`: Notebook containing the first implementation of data cleaning, clustering, and visualization <br>
`eeg-final.ipynb`: Notebook containing data cleaning, clustering, and final visualizations <br>
`eeg-presentation.pdf`: Contains final visualization process + presentation <br>
`eeg-viz.html`: Contains dashboard for the final visualization 

## Results 
The final visualization contains three charts that interact with one another. The first chart displays the average values of all channel recordings across all time points. In addition, the chart is also interactive and allows for the user to select a specific interval which is refelected on the second chart. The second chart, much like the first, displays the average values of all channel recordings across all time points and contains a legend that allows for the multi-selection of individual channels. The time interval selected on the first chart is reflected here as well as the multi-selection of channels from the legend. The third chart, which displays an EEG cap, allows for the user to view the location of each channel. At the bottom of the visualization, there are radio buttons that allow the user to select each individual cluster. The selection of a cluster is reflected on the second (displays millivolt recordings) and third charts (highlights the channels that fall into the selected cluster on the EEG cap). The Gaussian Mixture Model clustered the dataset into six distinct clusters which allow the user to find and demonstrate channel activity, compare trends, and locate channel outliers. 

## Preview
![Preview](https://github.com/abelasandovalg/eeg/blob/main/images/preview.png)

## Future Improvements 
1. The radio buttons used to select a cluster includes the option, "All". When selected, all of the data is reflected on the second chart, but not the third. Instead of displaying a blank EEG cap, Altair displays a random image from another cluster. 
2. Another feature that would interesting to implement would be a Fourier transform. A Fourier transform would allow the user to transform the data into alpha, beta, delta, and theta waves which can reflect certain states of brain activity. 
