<<<<<<< HEAD
# Character_Localization
=======
## How to train
Reference https://blog.roboflow.com/how-to-train-yolov8-on-a-custom-dataset/

I trained model on google colab:

    !pip install ultralytics

then:

    !pip install roboflow

    from roboflow import Roboflow
    rf = Roboflow(api_key="U3Z42yHcIhgZyHEkMP2o")
    project = rf.workspace("hannomocr").project("hannomdataset")
    version = project.version(1)
    dataset = version.download("yolov8")

Change file data.yaml after download: 

line 11 -> train: train/images

line 12 -> val: valid/images

then:

    !yolo task=detect mode=train model=yolov8n.pt data={dataset.location}/data.yaml epochs=50 imgsz=640

Output model is best.pt in folder runs/detect/train/weights.

## How to run

run the command:

    python main.py /images/test /labels/test

/images/test: is the path to test images folder

/labels/test: is the path to test labels folder
>>>>>>> 2a247a6 (Initial commit with existing code)
