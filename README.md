# Automatic-Number-Plate-Recognition--ANPR-
Automatic Number Plate Recognition (ANPR) Using YOLOv8 and easyOCR

![image](https://github.com/AarohiSingla/Automatic-Number-Plate-Recognition--ANPR-/assets/60029146/f9e79b40-b887-4804-85c3-380dbda7a2a7)

YOutube Video link: https://www.youtube.com/watch?v=1qVxaK1V074



!pip install ultralytics==8.0.0

!pip install easyocr

!git clone https://github.com/AarohiSingla/Automatic-Number-Plate-Recognition--ANPR-.git

cd Automatic-Number-Plate-Recognition--ANPR--main


#### To train your model on License plate detection:

from ultralytics import YOLO

###### Load a model
model = YOLO('yolov8n.pt')  # load a pretrained model (recommended for training)

###### Train the model
results = model.train(data='data.yaml', epochs=200, imgsz=640) 


#### Test the yolov8 model:

###### Load a pretrained YOLOv8n model
model = YOLO('ultralytics/runs/detect/train_model/weights/best.pt')

###### Run inference on video
model.predict('test_vid.mp4', save=True, imgsz=320, conf=0.2)



#### To perform Detection and Recognition (YOLOv8 + easyOCR) run the below command: 

!python predict_modified.py model='ultralytics/runs/detect/train_model/weights/best.pt' source='test_vid.mp4' 
