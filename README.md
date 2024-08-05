
## Dataset
### DroneVehicle

The dataset is available for download at the following link. Many heartfelt thanks for their meticulous dataset collection and expert labeling efforts!

[DroneVehicle]([https://github.com/ultralytics/yolov5](https://github.com/VisDrone/DroneVehicle))

Processed labels for our carefully organized dataset:

-[Label]  [download](https://pan.baidu.com/s/17tLn0D6yZkVqokMBpis1jw) password:5sow

Pre-training weights download:

-[Weight]  [download](https://pan.baidu.com/s/1PnmdKqIxPnTgK6yQ6WfwpA) password:zvi2


# INSTAllation 

* CUDA: 11.3

## Install 
**CUDA Driver Version ≥ CUDA Toolkit Version(runtime version) = torch.version.cuda**

a. Create a conda virtual environment and activate it, e.g.,
```
conda remove -n mmdetection --all
conda activate mmdet
conda install pytorch==1.10.1 cudatoolkit==11.3.1 torchvision==0.11.2 -c pytorch
```

```
pip install -r requirements.txt
cd utils/nms_rotated
python setup.py develop  #or "pip install -v -e ."
```
## train

```
python train.py

```
## Install DOTA_devkit. 

### Download DOTA_devkit. 

-[DOTA_devkit]  [download](https://pan.baidu.com/s/1MBW3DK6Vjx09T5dJdiXnig) password:peoe

**(Custom Install, it's just a tool to split the high resolution image and evaluation the obb)**
```
cd yolov5_obb/DOTA_devkit
sudo apt-get install swig
swig -c++ -python polyiou.i
python setup.py build_ext --inplace
```

## test

```
python valtest.py --save-json --name 'obb_demo6'
python tools/TestJson2VocClassTxt.py --json_path 'runs/val/obb_demo/best_obb_predictions.json' --save_path 'runs/val/obb_demo/obb_predictions_Txt'
python DOTA_devkit-master/dota_evaluation_task1.py 
```





