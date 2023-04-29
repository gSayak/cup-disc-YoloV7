# Cup and Disc segmentation using YOLO v7 instance segmentation
This repo uses YOLOv7 for segmentation of cup and disc from fundus image.

<img src= "https://github.com/gSayak/cup-disc-YoloV7/blob/main/assets/My%20project-1.jpg"></img>

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

<h2>Results in YOLO v7 model:</h2>

<img src="https://github.com/gSayak/cup-disc-YoloV7/blob/main/assets/results.png" style=""></img>

<h2>VS</h2>

<h2>Results in YOLO v5 model:<h2>
<img src="https://github.com/gSayak/cup-disc-Segmentation/blob/main/assets/results.png" style=""></img>

# Dataset

This repo has been trained on the RIM-ONE dataset. RIM-ONE DL is a unified retinal image database for assessing glaucoma using Deep Learning. The full paper is available in this publication of the Image Analysis and Stereology journal: https://www.ias-iss.org/ojs/IAS/article/view/2346

The directory structure followed is:

```
HOME/
└── dataset-name/
    ├── test/
    │   ├── images/
    │   │   ├── image-0.jpg
    │   │   ├── image-1.jpg
    │   │   └── ...
    │   └── labels/
    │       ├── image-0.txt
    │       ├── image-1.txt
    │       └── ...
    ├── test/
    │   ├── images/
    │   │   └── ...
    │   └── labels/
    │       └── ...
    ├── valid/
    │   ├── images/
    │   │   └── ...
    │   └── labels/
    │       └── ...
    └── data.yaml
    
  ```
 The repo was annotated manually using <a href="https://roboflow.com/">RoboFlow</a>

Link for annotated dataset:  <a href="https://drive.google.com/drive/folders/1_ilde9qcASPgxcNs6jEDFtRrYH3vcB4M?usp=sharing">Here!</a>

Annotation done by <a href="https://github.com/D0MINATRIX">Rajdeep Chatterjee</a>
  
# Steps to run segmentation on any Fundus image

For running this repo on Google Colab you will need to   
1. Clone the repo 
2. Upload the <a href="https://github.com/gSayak/cup-disc-YoloV7/blob/main/prediction-YOLOv7.ipynb">prediction-YOLOv7.ipynb</a> in a google drive
3. Open the prediction-YOLOv7.ipynb with Google Colab
4. Once the file gets opened in Colab, upload the fundus image you want to mask in Google colab either by using the upload button or by simple drag and drop
5. Copy the path of the fundus image that you uploaded and replace the `'path to/fundus.jpg'` with the path you copied in the earlier step or you can provide the URL of any image from the internet
```bash
!python segment/predict.py \
--weights '/content/cup-disc-YoloV7/weights/best.pt' \
--conf 0.25 \
--source '/path to/fundus.jpg'
```
6. After changing the source, click `Runtime` in the toolbar and click on `Run all` or you can use `Ctrl+F9` to run the notebook and get the desired result. 
7. The results will be stored in the `yolov7 -> runs -> predict-seg -> exp`
8. To display the image change the path of the filename in the `display.Image` to the location where your result is stored as mentioned in `step 7`
```bash
for imageName in glob.glob('/content/yolov7/seg/runs/predict-seg/exp/*.jpg')[:2]:
      display(Image(filename=imageName))
      print("\n")
```
9. The segmented image with masks on cup and disc will be shown to you
<img src="https://github.com/gSayak/cup-disc-YoloV7/blob/main/assets/fundus%20(1).jpg"></img>

