# Activity2Class
## [Eeli Susan](), [Esa Ollila]()

This code implements the ["Attention based end-to-end classifier for
universal human activity recognition"](https://about:blank) paper.

# Datasets

The separate datasets can be downloaded from their original sources:
 - [RealWorld (HAR) 2016](https://sensor.informatik.uni-mannheim.de/#dataset_realworld)
 - [Sussex-Huawei Locomotion Dataset 2018](http://www.shl-dataset.org/activity-recognition-challenge/)
 - [Human Activity Recognition Using Smartphones Data Set 2013](https://archive.ics.uci.edu/ml/datasets/human+activity+recognition+using+smartphones)

The folder `preprocessing_scripts` contains tools to convert the datasets to the following structure
```
dataset_name
├──train
│  ├─Acc_x.txt
│  ├─Acc_y.txt
│  ├─Acc_z.txt
│  └─Label.txt
├──test (optional)
│  ├─Acc_x.txt
│  ├─Acc_y.txt
│  ├─Acc_z.txt
│  └─Label.txt
├──validation (optional)
│  ├─Acc_x.txt
│  ├─Acc_y.txt
│  ├─Acc_z.txt
│  └─Label.txt
├──Label_names.txt
├──model (optional)
├──train_acc_results.npy (optional)
└──train_loss_results.npy (optional)
```
Each `Acc_[axis].txt` file contains rows with arbitrary length of samples, correspoding to sequences of accelerometer measurements. The `Label.txt` file must contain a label (integer) for each of the rows. Labels must be sequential, but do not have to start from 0 (this is automatically compensated). The `Label_names.txt` file should contain the names of each class in order of the integer labels. For joint classification use names with an underscore (i.e. ``label1_label2``). These are later split during results

If the test and validation folders are missing, the code automatically splits the training set into 50% train, 17% validation, and 33% testing data. If training and testing data is given, training is split into 80% training and 20% validation.

A trained model is stored as `model` and can be loaded if training is skipped
# Citation

# Implementation notes
The code is implemented in Python version 3.8.10 using PyTorch 1.10. Higher versions should be supported as well for the forseeable future.

# Licensing

Copyright (c) 2022 Eeli Susan, Esa Ollila

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

