# Setup

```bash
conda create -n env python=3.6 pip
conda activate env

pip install -r requirements.txt
git clone https://github.com/matterport/Mask_RCNN.git
git clone https://github.com/philferriere/cocoapi.git
pip install git+https://github.com/philferriere/cocoapi.git#subdirectory=PythonAPI
```

# Test detection and color splash

Past directory cigarette in Mask_RCNN/samples

Go to ```Mask_RCNN/samples/cigarette```

## Dection with jupyter notebook

```bash
jupyter notebook
```

Run ```demo.ipynb```

## Dection in CLI

Run on a random image from directory dataset/test
```bash
python cigarette.py detect --weights=./mask_rcnn_cigarette.h5
```
Run on a specified image
```bash
python cigarette.py detect --weights=./mask_rcnn_cigarette.h5 --image=./dataset/test/smoking_0297.jpg
```

Apply color splash on a specified image
```bash
python cigarette.py splash --weights=./mask_rcnn_cigarette.h5 --image=./dataset/test/smoking_0297.jpg
```

# Train

## Jupyter notebook

```bash
jupyter notebook
```

Run ```train_cigarette.ipynb```

## CLI
```bash
python cigarette.py train --dataset=./dataset --weights=coco
```

# Config and output
Some informations about the config when we trained this model
```
BATCH_SIZE: 1
LEARNING_RATE: 0.001
ROI_POSITIVE_RATIO: 0.33
STEPS_PER_EPOCH: 200
TRAIN_ROIS_PER_IMAGE: 200
VALIDATION_STEPS: 50
```

A complete display of this will appear if you run detection or train
You can see screenshots of testing in ```test_output``` directory