# MobileNet-Caffe-Classification

### Introduction

Model prototxt files copy from https://github.com/shicai/MobileNet-Caffe and add some other files for training and inference conveniently. You can train mobilenet for classification task easily use this code.

[This is a Caffe implementation of Google's MobileNets (v1 and v2). For details, please read the following papers:

- [v1] [MobileNets: Efficient Convolutional Neural Networks for Mobile Vision Applications](https://arxiv.org/abs/1704.04861)
- [v2] [Inverted Residuals and Linear Bottlenecks: Mobile Networks for Classification, Detection and Segmentation](https://arxiv.org/abs/1801.04381)
]

### File Structure
```
+-- ckpt
|   +-- pretrain
|       |   +--  mobilenet.caffemodel
|       |   +--  mobilenet_v2.caffemodel
+-- data
|   +-- get_train_data_list.sh  # util script for data
|   +-- your_data_dir
+-- prototxt
|   +-- m1_solver.prototxt
|   +-- m2_solver.prototxt
|   +-- v1
|       |   +-- mobilenet_deplpoy.prototxt
|       |   +-- mobilenet_train.prototxt
|   +-- v2     
|       |   +-- mobilenet_v2_deplpoy.prototxt
|       |   +-- mobilenet_v2_train.prototxt
+-- README.md
+-- LICENCE
+-- train.sh
+-- infer.py
```
### Usage
##### 1. Prepare data for classification task

 Put all images into one dircectory (your_data_dir), use file name save your data's label
 
 ```
 #before the separator "_" is your class index.
 /data/1_xxx.jpg
 /data/0_xxx.jpg
 /data/2_xxx.png
 ...
 ```
 Run this command then you will get a file named trainval.txt
 
 ```
 sh get_train_data_list.sh your_data_dir
 ```
 Data format for training
 
 ```
 /imagepath class_index
 # Example:
 /data/1_pos.jpg 1
 /data/0_neg.jpg 0
 ```

##### 2. Train model
Run command

```
sh train.sh mobilenet
# or
sh train.sh mobilenet_v2
```



