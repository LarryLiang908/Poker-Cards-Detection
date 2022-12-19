# Poker-Cards-Detection

This is a repository created for DS301 fall 2022 final project by Larry Liang and Junru Lu.

## Project Description

Nowadays casinos are streaming Texas-Holdem games on the Internet such as Youtube and Twitch. While the games are conducted in person, casinos recoginize poker cards with camera placed in front of each player and show audiences the cards they have.

<img width="1920" alt="207722953-b8878fd1-ade5-4df5-bfe9-0060b18cce89" src="https://user-images.githubusercontent.com/90345344/208335204-c5cd0f7d-2ff2-4c7f-9649-774392f2aa67.png">


Our goal is to recognize poker cards in Texas Holdem stream with high accuracy.

## Repository and code structure
```
├── data/ # Dataset of poker cards
├── models # YOLO v7 model
├── train.py # the training script
├── detect.py # the evaluation script
├── export.py # export model
├── utils # utils needed for the model
├── requirements.txt # environments required for the model
|   ...
```

## Example commands to execute the code    
### train model
```bash
!python train.py --batch 16 --epochs 55 --data {dataset.location}/data.yaml --weights 'yolov7_training.pt' --device 0 
```
### Run evaluation
```bash
!python detect.py --weights runs/train/exp3/weights/best.pt --conf 0.1 --source {dataset.location}/test/images
```

## Result
<img width="955" alt="Screen Shot 2022-12-18 at 21 36 12" src="https://user-images.githubusercontent.com/90345344/208336753-0f126bc3-465d-4b8c-a3a8-7ad9b4318c2c.png">

Under the condition that the environment is complex enough, we have achieved a good poker recognition effect, making the recognition speed on each test set less than 15ms. This is only a model that has been trained for 55 epoch. I believe that after fine-tuning the model training, we will achieve better results. Yolov7 meets our initial recognition goals, fast and accurate.


## Acknowledgements

### Pretrain weight
https://github.com/WongKinYiu/yolov7/releases/download/v0.1/yolov7_training.pt

### Yolov7
https://github.com/WongKinYiu/yolov7


