# Cup and Disc segmentation using YOLO v7 instance segmentation
This repo uses YOLOv7 for segmentation of cup and disc from fundus image.
<img src="https://github.com/gSayak/cup-disc-YoloV7/blob/main/assets/My%20project-1.jpg", style""><img>

# What is Cup and Disc

In ophthalmology, the cup and disc refer to the optic nerve head and surrounding retina in the back of the eye. The cup is the center of the optic nerve head, while the disc is the surrounding tissue. The relationship between the size of the cup and disc can provide important information for diagnosing and monitoring certain eye conditions, such as glaucoma.

Doctors often use fundus imaging, a non-invasive imaging technique that captures detailed images of the retina, to assess the cup-to-disc ratio (CDR). A high CDR can indicate glaucoma or other optic nerve disorders, which can cause vision loss if not detected and treated early.

However, the process of manually analyzing fundus images to measure the CDR can be time-consuming and prone to human error. This is where automated segmentation algorithms like Mask R-CNN, YoloV5 and YoloV7 can be useful, as they can accurately and efficiently segment the cup and disc in fundus images, enabling faster and more reliable diagnosis of eye diseases.

# Difference from previous project of Detection with <a href="https://github.com/gSayak/cup-disc-YoloV5">YOLOv5</a>

This instance segmentation model is based on the YOLOv7 architecture and has been trained on the same dataset of fundus images for the purpose of segmenting the cup and disc regions for the detection of glaucoma. The YOLOv7 architecture is an improvement over the previous YOLOv5 architecture, with better accuracy and faster training times.

<h4>Features and Improvements:</h4>

Compared to the previous YOLOv5 architecture, the YOLOv7 model has several features and improvements that make it a better choice for instance segmentation tasks:

1. Improved Architecture: The YOLOv7 architecture is an improvement over the YOLOv5 architecture, with better feature extraction and higher accuracy.

2. Faster Training: The YOLOv7 model trains faster than the YOLOv5 model, with faster convergence and better use of resources.

3. Higher Accuracy: The YOLOv7 model has higher accuracy than the YOLOv5 model, with better performance on challenging datasets.

4. Improved Object Detection: The YOLOv7 model has improved object detection capabilities, with better detection of small and occluded objects.

