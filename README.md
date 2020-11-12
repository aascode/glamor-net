# Global-Local Attention for Emotion Recognition



# Getting Started
If you want to validate our result or training by yourself. We've already setup all the process in the google colab link below.\
Some of the examples in PASCAL SBD dataset. 

![image](dataset_examples/ex1.png)

## Requirements
- Python 3
- Install [tensorflow](https://www.tensorflow.org/install). (or tensorflow-gpu) >= 2.0.0 
- Install some other packages
```Shell
pip install cython
pip install opencv-python==4.3.0.36 matplotlib numpy==1.18.5 dlib
```




4. Download our prepared dataset from google drive [PASCAL_SBD.zip](https://drive.google.com/file/d/1uyZtl6LDxbgHC7ctDl0rbGlxOOrvCssG/view?usp=sharing).
Extract and put it into data/sbd folder. (the folder should have sbd/imgs and <anotation_files>.json)
5. Run the desired command above for training or evaluating.
Notice that the orignal [PASCAL SBD](http://home.bharathh.info/pubs/codes/SBD/download.html) using the voc's annotation format.\
To run this code, we've converted it into coco's format. we put the prepared dataset download link in the tutorial below

# Datasets download
We provide the original images and extracted faces (a .txt file with 4 bounding box coordinate) in the NCAERS dataset.
download at []()
# Running
Our code supports these types of execution with argument -m or --mode:
```
#extract faces from <train, val or test> dataset (specified in config.py)
python run.py -m extract dataset_type=train

#train the model with config specified in the config.py
python run.py -m train 

#evaluate the trained model on the dataset <dataset_type>
python run.py -m eval --dataset_type=test --trained_weights=path/to/weights
```

# Evaluation
Our trained model is available at ```weights/glamor-net/Model```.

```
#Evaluate our model in the test set
python run.py -m eval --dataset_type=test --trained_weights=weights/glamor-net/Model
```
Run this command to 

# Training 
Firstly please extract the faces from train set (val set is optional)
- Specify the path to the dataset in config.py (train_images, val_images, test_images)
- Specify the desired face-extracted output path in config.py (train_crop, val_crop, test_crop)
- Perform face extraction on both dataset_type by running the commands:
```
python run.py -m extract --dataset_type=<train, val or test>
```
Train the model:
```
# Train a new model from sratch
python run.py -m train 

# Continue training a model that you had trained earlier
python run.py -m train --resume=path/to/trained_weights

# Resume the last checkpoint model
python run.py -m train --resume=last
```

# Use the help option to see a description of all available command line arguments











