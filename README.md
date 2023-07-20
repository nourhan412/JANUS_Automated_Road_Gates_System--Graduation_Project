# JANUS Automated Road Gates System (Graduation Project)
### This repository provides concise details about my graduation project, highlighting my contribution in building Computer Vision models for Egyptian license plate number detection and vehicle classification within the Automated Road Gates System.


---
![Project Maquette](images/maquette.jpg)


## Project Overview

Janus Automated Road Gates System is a graduation project that aims to resolve the manual road toll collection issues in Egypt, managed by human workers.

The System seamlessly integrates various cutting-edge technologies to create a robust and efficient solution. The system comprises the following components:

- **Mobile App**: The user-friendly mobile application enables users to see gates that are on the road, find information about their toll prices, allows them to pay these tolls before arriving at the gate and a lot of services.

- **Embedded Systems**: The system utilizes embedded devices (such as Ultrasonic Sensor, Servo Motor and RFID Reader) which together form the gate control system.
  
- **Backend**: The backend system, acts as the central hub for data storage, communication, and coordination. It handles API requests from the mobile app and embedded systems, providing seamless integration between different components.

- **Computer Vision Models**: The system lies in the AI models for license plate number detection and vehicle classification. These models process the captured images from the embedded systems and provide accurate results for vehicle identification.
  

## Team Members

- Ahmed Rashed
- Mina Maher
- Nourhan Abosaeed
- Mahmoud Bahaa
- Ahmed Gamal
- Ahmed Roshdi
  

## Project Documentation and Prototype in Action

- **Project Overview Video**: To get an in-depth understanding of the Automated Road Gates System project idea and witness the maquette (prototype) in action, please watch our [project overview video](https://www.youtube.com/watch?v=kQZk_uqAZas).

- **Project Documentation**: For more detailed information about the system's development, including AI models, mobile app, backend, and embedded systems, please refer to our [project documentation](https://drive.google.com/file/d/1yGR7fPZQpwTrd-XG2_s_ieb8_UddPjKI/view).

## Computer Vision Pipeline Overview

![Pipeline Overview](images/Pipeline.png)


The Computer Vision Pipeline operates as follows: Upon receiving an image captured at the road gates, it goes through 3 models that work together to extract the needed data.

The first model executes a vehicle type classification , efficiently identifying the vehicle's category, such as cars, trucks, motorcycles, and more. This classification is paramount, as the toll calculation depends on the type of vehicle detected.

The second model encompasses two stages: the initial sub-model detects the precise position of the license plate within the image and subsequently crops it for further analysis. Subsequently, the cropped license plate is forwarded to the second sub-model, which employs a detection model to accurately recognize and extract the alphanumeric characters from the plate.

## Egyptian License Plate Detection

I successfully implemented and evaluated Inception-ResNet-v2 and YOLOv5 models for Egyptian License Plate Detection using the same dataset. The dataset utilized in this task consists of 2087 vehicle images, including cars, buses, trucks, microbuses, and minibuses. Each image is accompanied by an annotation text file containing the class label and the bounding box coordinates of the license plate within the image. The images were captured using various cameras, at different times, with varying lighting conditions and backgrounds. The Inception-ResNet-v2 model demonstrated promising performance on this dataset, achieving a loss of 0.0020 and an accuracy of 0.957 on the test set. Additionally, YOLOv5 achieved an exceptional mAP score of 0.9946.

---
## License Plate Characters Recognition

In the Egyptian License Plate Characters Recognition task, we employed two state-of-the-art object detection algorithms on a dataset containing 1978 images of Egyptian license plates, each with corresponding annotation files. These annotations specify the character label and bounding box coordinates for each character on the license plate.
After detecting the license plate using the object detection algorithm, we cropped the bounding box to extract the plate. This cropped image was then fed as input to another model trained for character recognition. The models, Faster R-CNN and YOLOv7, were thoroughly evaluated on this task, and both exhibited exceptional performance.
The Faster R-CNN model achieved an impressive accuracy rate of 97% when evaluated on a separate test dataset.
On the other hand, YOLOv7 achieved a mean Average Precision at an IoU threshold of 0.5 (mAP@0.5) of 0.988 for all classes in the test set, solidifying its position as a strong contender in the task of Egyptian Plate Characters Recognition.

---
## Vehicle Type Classification

For the Egyptian Vehicles Type Classification task, my teammate and I utilized two separate datasets. The first dataset was acquired through web scraping from various online sources, while the second dataset was manually collected, comprising images of vehicles with similar characteristics commonly found in Egypt.
We applied three different models, namely RESNET50, VGG16, and YOLOv7, to perform vehicle type classification on both datasets. 
The RESNET50 model demonstrated consistent and satisfactory results on both datasets. On dataset 1, it achieved a test loss of 0.5 and a test accuracy of 0.927. Similarly, on dataset 2, the model attained a test loss of 0.59 and a test accuracy of 0.90, indicating its reliable performance in vehicle type classification.
The VGG16 model also exhibited strong performance on both datasets. On dataset 1, it achieved a test loss of 0.6 and a test accuracy of 0.92, while on dataset 2, the model obtained a test loss of 0.54 and a test accuracy of 0.93, showing slightly improved performance on the second dataset.
In terms of object detection, the YOLOv7 model delivered impressive results with an overall mean Average Precision (mAP) of 0.98. Although the "truck" class had a slightly lower mAP of 0.96, the model demonstrated high precision and recall for all classes, emphasizing its accuracy in detecting and classifying vehicles in the input images.

### Vehicle Classification Using License Plate Color

After building different models to classify the images based on the vehicles imaged, we have now shifted our focus to detecting the vehicle type based on the license plate color.
we utilized the same dataset as in the license plate character recognition task, as publicly available datasets specifically focused on license plate color detection in Egyptian vehicles were scarce.
However, we encountered a challenge with the dataset, as more than 90% of the images depicted license plates with a light blue background, typically used for private cars. This posed a difficulty in training a deep learning classification model to accurately detect different vehicle types based on license plate color.
To overcome this challenge and improve model accuracy, we experimented with various approaches. One of these approaches involved using Adobe Photoshop to edit license plate colors, creating a more diverse dataset. Additionally, we leveraged the OpenCV library to generate new license plate images with different colors. Moreover, we applied image processing techniques directly to the existing dataset to further enhance its diversity.

The plate character recognition model achieved an impressive accuracy of 95%. While ResNet50 exhibited a respectable test accuracy of 94%. In contrast, YOLOv7 outperformed the other models by accurately classifying the colors of license plates, achieving a remarkable accuracy of 98% on the test set.

---
## Deployment

---
### Copyrights

>Copyright (c) 2022-2023 Faculty of Computers and Informatics Tanta University 
