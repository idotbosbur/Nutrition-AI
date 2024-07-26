# Food Recognition AI

This project uses the Nvidia Jetson Nano to recognize food items from a live camera feed and display their nutritional information in real-time. This project shows the Jetson Nano's capability to perform image classification and overlay relevant data on video streams. 

![image](https://github.com/user-attachments/assets/c723f1e6-cd3b-41e6-959e-52c80985197d)

^ Here in this image, you can see the overlay of the nutrition facts provided.


## The Algorithm

**1. Image Capture:**

  The algorithm captures frames from a live camera stream using the video source class from the jetson_utils library. 
  
**2. Image Classification:**

  Each captured frame is passed through a pre-trained deep neural network (DNN) model using the imageNet class from      the jetson_inference library.

  The DNN model, specified by the user (default is GoogLeNet), processes the image and outputs the predicted class       along with the confidence score.

**3. Nutritional Information Mapping:**

  The predicted class label is compared with a predefined list of food items.
  If a match is found, the corresponding nutritional information is retrieved from the Food class instances.

**4. Text Overlay:**

  The nutritional information is formatted and overlaid onto the image frame using the cudaFont class from the           jetson_utils library.

  This overlay includes details such as calories, total fat, saturated fat, trans fat, cholesterol, sodium, total        carbohydrates, dietary fiber, total sugars, and protein.

**5. Rendering:**

  The annotated image frame is then rendered and displayed using the videoOutput class from the jetson_utils library.


**Code Dependencies**


1. jetson-inference: Provides the imageNet class for image classification.

2. jetson-utils: Provides utilities for video capture (videoSource), video output (videoOutput), and text overlay      (cudaFont).

3. argparse: Used for parsing command-line arguments.

**Detailed Steps in the Code**

Class Definition:

  The Food class is defined to store the nutritional information for different food items.

Food Information Initialization:

  A list of food items and their nutritional information is created. Instances of the Food class are initialized for     each food item.

Command-line Argument Parsing:

  The script parses command-line arguments to get the input and output streams and the DNN model to use.

Network and Video Initialization:

 ** A.** The image classification network is initialized with the specified model.
 ** B.** Video sources and outputs are created for capturing and rendering video streams.

Image Processing Loop:

 ** A.** The script enters a loop where it captures images from the video source.
 ** B.** Each image is classified using the DNN model.
 ** C.** If the predicted class label matches a food item, its nutritional information is retrieved and overlaid on the image.
 ** D.** The annotated image is rendered to the output stream.


https://github.com/user-attachments/assets/1e75e40e-6e75-4994-873f-0fc2b253f53f


