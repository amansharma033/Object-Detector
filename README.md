Object Detection
Detect objects on images/video frames.

Setup
clone repo git clone https://github.com/amansharma033/Object-Detector.git
navigate to object detector directory cd vehicle-distance-estimation/object-detector/
install requirements pip install -r requirements.txt
setup environment python setup.py
Training
Dataset
download dataset bash scripts/download-flir-dataset.sh
format dataset as YOLOv5 format python format-dataset.py
Fine-tuning YOLOv5s
create YAML configuration file python create-yaml.py
modify yolovs YAML file python configure-yolo-yaml.py
train model on our custom dataset python train.py --epochs 50 --data dataset.yaml --cfg yolov5s.yaml
Detection
make detections on images/videoes using our training weights.

download our pre-trained model's weights gdown --folder 10jpVGSHGILDt85QGf5KwHji0sUjZXbWR
detect objects on input video python detect.py --save-txt --weights training-results/weights/best.pt --conf 0.4 --source video.mp4
Generate Objects Coordinates Sheet
Frames on rows & classes on columns. Each cell has all center coordinates of the detected objects in a frame on a row from class on a column.

generate sheet from text labels python generate-coordinates-sheet.py
