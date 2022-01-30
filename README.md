# Image-Classification-using-Machine-Learning

## Motivation :
 This project is aims on enhancing the image classification by integrating it with server and UI to facilitate an end-to-end project. The UI accepts the image of a sports celebrity and performs image classification to find out which celebrity it is. For the scope of this project, 5 celebrities are considered.


## Technologies Used:

 Language : Python <br>
 Data Cleaning : Numpy and OpenCV <br>
 Data Visualisation : Matplotlib & Seaborn <br>
 Model Building : Sklearn for model building <br>
 Server : Python Flask <br>
 UI : HTML/CSS/UI <br>
 IDE : Jupyter notebook, visual studio code and pycharm as IDE <br>
 Deployment : AWS <br>


## Data Collection:
 
 Data Collection is a primary area of importance in any data science project because the efficiency of any model is dependent heavily on the quality of the data that is being used. There are four broad ways in which data can be collected:
  1. Manual download and labelling of data - a very laborious and time consuming process.
  2. Using web scraping to collect data across the internet -  Web scraping is a grey area as it may be deeemed illegal depending on how the data is gathered and what is done with the data. (Refer : https://www.rocketlawyer.com/gb/en/blog/to-scrape-or-not-to-scrape/)
  3. Fatkun tool - A good tool that is used for bulk download of images.
  4. Lastly, the data can be bought by third party vendors - although expensive, this ensures quality and legality of the data being used.

## Data Cleaning:

As this project deals with recognising people, we will check the images that clearly show a face with two eyes. For this OpenCV is used and the Haarcascade technique is used for face detection. Most data cleaning, around 80-90% is done using python while some manual effort is needed to determine more patterns. In large projects, it is done by crowdsource workers. As a part of this process, the images are cropped to contain only the face of the sports celebrity (as the face is the main attribute for the later steps). A bit of human remediation is involved here as the check the cropped folders to remove any non-related images (pictures of anushka are fetched when images of Virat is searched) 


## Feature Engineering:
Once the data is cleaned, we perform a wavelet transform and feature engineering to train our model. Performing wavelet transform to the cropped image faciliates extraction of more meaningful features of the image. But even the raw cropped images have features, so the wavelet transform and raw image are stacked up. This new combined image will be further used for image training.
 
 
## Model Training:
After getting the feature engineered data, GridSearch CV is used to find the best performing model between SVM, random forest and logistic regression. The best performing model is then exported to be used by the python flask server.

## Creating the Flask Server:
Python flask is a light weight web server. In this section, flask server that will use the trained (exported) model and perform image classification. UI will talk to this backend server and perform image classification. The results will then be displayed in the UI.


## Building a website
The frontend is built using HTML/CSS/Javascript. It will make HTTP calls to the backend using JQuery. HTML determines the anatomy of the application like the buttons, controls and layout, CSS defines the style guide for the application i.e. colors, look and feel etc, Java script consists of dynamic code which is used to make calls to backend. The front end of the website provides a simple portal that facilitates uploading of image and calculation of classification score.


## Model Deployment on AWS
This step involves the deployment of the machine learning classification model on the AWS EC2 server. For AWS EC2 we will use ubuntu server on which we will deploy our web application as well as python flask server. The HTTP requests will be served by the nginx server. Using nginx reverse proxy /api requests will be routed to python flask server running on same machine.
