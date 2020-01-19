# Traffic-Light-Classifier
In this project , Traffic lights have been classified (Red, Yellow , Green) using Computer Vision fundamentals.

## Installing Dependencies
* opencv  -  `pip install opencv-python `

## Data
Data is compressed and uploaded

## Sample from the data
![sample](images/all_lights.png) 

## Classification Steps

* **Loading and Visualizing the Traffic Light Dataset**

    This traffic light dataset consists of 1484 number of color images in 3 categories - red, yellow, and green. As with most human-sourced data, the data is not evenly distributed among the types. There are:

    - 904 red traffic light images
    - 536 green traffic light images
    - 44 yellow traffic light images

    _Note: All images come from this [MIT self-driving car course](https://selfdrivingcars.mit.edu) and are licensed under a 9Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/)._
* **Pre-process the Data**

    After loading in each image, you have to standardize the input and output!

    **Input**

    This means that every input image should be in the same format, of the same size, and so on. We'll be creating features by performing the same analysis on every picture, and for a classification task like this, it's important that similar images create similar features!

    **Output**

    We also need the output to be a label that is easy to read and easy to compare with other labels. It is good practice to convert categorical data like "red" and "green" to numerical data.

    For labels we use one-hot encoding . A red light should have the label: 1, 0, 0. Yellow should be: 0, 1, 0. Green should be: 0, 0, 1. These labels are called **one-hot encoded** labels.
* **Visualize the standardized data**

    Display a standardized image from STANDARDIZED_LIST and compare it with a non-standardized image from IMAGE_LIST. 

* **Feature Extraction**

    Now we use opencv library to convert images to _HSV color_ space and extract features from it .
    We will be masking parts of image too
    
    * **Displaying Histogram of different Images**

        In this approach we understand what happens to **V-channel** of HSV color space when masked with all 3 (red , yellow , green ) masks (on upper, mid, lower).

        V-channel is responsible for brightness in the image , which means **Histogram of V- channel if compared to red , green ,yellow masks on same image , will spike only on the correct mask . for green light - Histogram of v channel of only green mask will spike** 
* **Classification and Visualizing Error**

    Accuracy of this model currently is at 95%, which can be improved to 99%.
    Further more this approach is only to understand how v-channel works .
