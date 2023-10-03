# TextExtractionMachineLearning

#Introduction

This documentation outlines a Python script designed to perform optical character recognition (OCR) and text extraction from images while employing various image preprocessing techniques. It utilizes libraries such as OpenCV, Google Cloud Vision, and Pillow to enhance image quality and readability, making it particularly effective at extracting text accurately from images.

#Prerequisites
Before using this code, ensure that you have met the following prerequisites:

Python 3.x
Google Cloud SDK
Required Python packages (install using pip):
google-cloud-vision
opencv-python
pillow
matplotlib
numpy
pandas

you can install these packages by using : 
!pip install google-cloud-vision
!pip install opencv-python
!pip install pillow
!pip install matplotlib
!pip install numpy
!pip install pandas

#Set up Google Cloud credentials by specifying the path to your service account JSON key file in the os.environ['GOOGLE_APPLICATION_CREDENTIALS'] variable.

#Code Overview
This code performs the following main tasks:
Imports necessary libraries and sets up the Google Cloud Vision client for text detection and OCR.
Defines a function resize_image(image, new_size) to resize input images while maintaining their aspect ratio and filling any extra space with white pixels to ensure consistent processing.
Implements an image_prepro(image) function that preprocesses images in the following steps:

-Resizes the image.
-Normalizes pixel values.
-Applies skew correction.
-Adjusts the image's resolution.
-Denoises the image.
-Converts the image to grayscale.
-Applies binarization to create a binary image.
-Displays the preprocessed image.
-Defines a process_image(image_path) function to process a single image:

Reads the image file.
Calls image_prepro() to preprocess the image.
Uses Google Cloud Vision to detect text within the preprocessed image.
Returns the extracted text.
Provides a process_images(image_paths) function to process multiple images and save the results to an Excel file:

Iterates through a list of image file paths.
Calls process_image() for each image.
Stores the results (image path and extracted text) in a Pandas DataFrame.
Exports the DataFrame to an Excel file named 'extracted_text.xlsx'.
In the __main__ block, the code demonstrates how to use the functions:

Specifies a list of image file paths (images) to be processed.
Calls process_image() for an individual image (image).
Prints the extracted text for demonstration purposes.


#Usage

-Ensure that you have met all the prerequisites mentioned above, including setting up Google Cloud credentials.
-Define the list of image file paths (images) that you want to process.
-Execute the code, and it will preprocess the images, extract text using Google Cloud Vision, and display the extracted text.
-To process multiple images and save the results to an Excel file, call the process_images() function and provide a list of image file paths as an argument.



#Example Output
When you run the code, it will:

-Display the preprocessed images with annotations.
-Print the extracted text from individual images.
-Save the results, including image file paths and extracted text, to an Excel file named 'extracted_text.xlsx'.
-The code's image preprocessing and OCR capabilities contribute to improved text extraction accuracy from images.

#Conclusion
This Python script serves as a valuable tool for extracting text from images with enhanced accuracy. 
By leveraging various preprocessing techniques and the Google Cloud Vision API, it ensures that text is extracted efficiently and effectively from a range of image sources, making it suitable for tasks such as digitizing documents, extracting information from images, and more.
