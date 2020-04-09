# Handwritten-Digit-Recognition
Hand written digit recognizer using Python 3.8. GUI based drawable console.


# Files
The repository contains 3 files. 
1. train_model.py : Python code file for training the neural network.
2. gui_console.py : Python code for creating the GUI console aand predicting inputs.
3. mnist.h5 : Pretrained weights file in hdf5 file formart

## Libraries
1. Keras
```
pip install Keras : Windows 
sudo pip3 install keras : Linux
```
2. Tkinter
```
pip install python-tk : Windows
sudo apt-get install python3-tk : Linux
```
3. Numpy
```
pip install numpy : Windows
sudo apt install python-numpy : Linux 
```
Other Libraries
```
PIL, win32gui
```
## Neural Network Architecture

Sequential Model.
```mermaid
graph LR
A(Input Layer) 
B{1st Convolution} 
C[MaxPool]
D{2nd Convolution}
E[MaxPool]
F((Flatten - A))
A --> B
B --> C 
C --> D
D --> E
E --> F
```
```mermaid
graph LR
J((Flatten - A))
G{Dense 1}
H{Dense 2}
I{Dense 3}
0((0))
1((1))
2((2))
3((3))
4((4))
5((5))
6((6))
7((7))
8((8))
9((9))

J --> G
G -- Dropout --> H
H -- Dropout --> I
I --> 0
I --> 1
I --> 2
I --> 3
I --> 4
I --> 5
I --> 6
I --> 7
I --> 8
I --> 9
```

## System Working
The model uses mnist dataset which contains 60000 handwritten digit images. Before feeding the nueral newtwork with the images, they are pre-processed. Several convolutional layers and pooling layers are applied and the output of the 2nd max pooling layer is flattened to feed the neural network input nodes. 
The dense layers are the main layers of the neural network which are followed by a dropout value to prevent the model from over fitting. 10 epochs gives an average accuracy of 0.9981. 
Trained weights are stored in a file named mnist.h5.
>Note: The provided file is a pretrained file. It is recommended to retrain the entire model with >=8 epochs to increase accuracy of the system.

The GUI console is developed using the tkinter library. Input is a drawable white screen where the user can draw the numbers and check for the prediction.
>Note: If you are using Jupyter Notebook, the console will not pop on the screen. You will find the running file on the taskbar of your operating system.

