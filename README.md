# Rank Face
A deep learning based model to judge the AQ, Appearance Quotient, of faces. (For Chinese Young Girls Only)
## Installation

```
apt-get install python-dev python-pip -y
pip install numpy scipy
pip install tensorflow keras
pip install h5py
apt-get install python-opencv
# for macOS use 'brew install opencv'
# for Windows try the installation tutorial from opencv official website
git clone https://github.com/Entropy-xcy/RankFace
cd ./RankFace
wget http://entropy-xcy.bid/faceRank.h5
```

## Demo
```
python main.py girls.jpg
```
Here is the output
![](demo.jpg)

## Training
It is highly recommended to train the model yourself. Some accuracy issues may happen if the platform you have is different from the trainer's.
```
rm ./faceRank.h5
wget http://entropy-xcy.bid/dataset.zip
unzip dataset.zip
rm dataset.zip
# You may change parameters in the script.
python train.py
```

## Model Summary:
```
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
conv2d_1 (Conv2D)            (None, 128, 128, 32)      896       
_________________________________________________________________
activation_1 (Activation)    (None, 128, 128, 32)      0         
_________________________________________________________________
conv2d_2 (Conv2D)            (None, 126, 126, 32)      9248      
_________________________________________________________________
activation_2 (Activation)    (None, 126, 126, 32)      0         
_________________________________________________________________
max_pooling2d_1 (MaxPooling2 (None, 63, 63, 32)        0         
_________________________________________________________________
dropout_1 (Dropout)          (None, 63, 63, 32)        0         
_________________________________________________________________
flatten_1 (Flatten)          (None, 127008)            0         
_________________________________________________________________
dense_1 (Dense)              (None, 128)               16257152  
_________________________________________________________________
activation_3 (Activation)    (None, 128)               0         
_________________________________________________________________
dropout_2 (Dropout)          (None, 128)               0         
_________________________________________________________________
dense_2 (Dense)              (None, 1)                 129       
=================================================================
Total params: 16,267,425
Trainable params: 16,267,425
Non-trainable params: 0
_________________________________________________________________
```
