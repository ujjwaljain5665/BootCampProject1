# Table Of Contents
-------------------
*
 Introduction
*
 Requirements
* 
Installation
* 
Code
# 
Introduction
--------------
In this project, I have taken an image and take the angle as input from the user and then rotate the image at the given angle in anti-clockwise direction.

# Requirements
--------------
This module requires the following modules:

* OpenCV
 
#Installation
--------------
* Install Visual Studio 2019
* Install OpenCV

# Configuration
---------------
To use OpenCV features in Visual Studio, we have to add additional include directories and define the path of various include directories into the properties of project in Visual Studio.

# Code
------
C++



#include <opencv2/highgui/highgui.hpp>

#include <opencv2/imgproc/imgproc.hpp>

#include <iostream>


using namespace cv;

using namespace std;


Mat rotate(Mat src, double angle)   //rotate function returning mat object with parametres imagefile and angle    

{
    Mat dst;      //Mat object for output image file
    
      Point2f pt(src.cols / 2., src.rows / 2.);          //point from where to rotate    
    
      Mat r = getRotationMatrix2D(pt, angle, 1.0);      //Mat object for storing after rotation
          warpAffine(src, dst, r, Size(src.cols, src.rows));  ///applie an affine transforation to image.
       return dst;         //returning Mat object for output image file

}


int main()

{
   
 Mat src = imread("C:\\Users\\RAVI\\Desktop/elephant.jpg");  //reading image file in mat object
    
    
 Mat dst;      //Mat object for output image file
    
 int angle;
    
 cout << "Enter the angle (in degree): ";
    
 cin >> angle;
    
 dst = rotate(src, angle);       //rotating image with inserted degree angle
    
    
 imshow("Original File", src);          //displaying input image file
    
 imshow("Rotated File in Anticlockwise Direction", dst);         //displaying output image file
    
waitKey(0);                     //to exit press escape
    
return 0;

}


In this code, I have selected a photo and printed both the original file and rotated file.