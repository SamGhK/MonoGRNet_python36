# MonoGRNet
with Python 3.6 and Tensorflow r.1.14

## MonoGRNet: A Geometric Reasoning Network for 3D Object Localization

This is an updated version of [MonoGRNet](https://github.com/Zengyi-Qin/MonoGRNet). The original version is based on Python 2.7 and Tensorflow 1.4. Currently, I am using this Model for my own project and needed to update/adopt the code to Python 3.6 and Tensorflow 1.14. Please check the original Repository under https://github.com/Zengyi-Qin/MonoGRNet

<br/>

### Prerequisites
- Ubuntu 18.04
- Python 3.6
- Tensorflow r1.14

### Install
Clone this repository
```bash
git clone https://github.com/SamGhK/MonoGRNet_python36.git
```

Download the [Kitti Object Detection Dataset](http://www.cvlibs.net/datasets/kitti/eval_object.php?obj_benchmark=3d) ([image](http://www.cvlibs.net/download.php?file=data_object_image_2.zip), [calib](http://www.cvlibs.net/download.php?file=data_object_calib.zip) and [label](http://www.cvlibs.net/download.php?file=data_object_label_2.zip)) and place it into `data/KittiBox`. The folder should be in the following structure:
```
data
    KittiBox
        training
            calib
            image_2
            label_2
        train.txt
        val.txt
```
The train-val split `train.txt` and `val.txt` are contained in this repository.
 
Compile the Cython module and download the pretrained model:
```bash
python setup.py
```

### Training and evaluation
Run the training script and specify the GPU to use:
```bash
python train.py --gpus 0
```
The evaluation is done during training. You can adjust the evaluation intervals in `hypes/kittiBox.json`.

### Visualization
```bash
cd visualize && mkdir visualize
python visualize.py
```

### Acknowledgement
I would like to thank the original Authors for their great job and implementation. MonoGRNet(https://github.com/Zengyi-Qin/MonoGRNet)

