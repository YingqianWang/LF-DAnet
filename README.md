## DistgSSR: Disentangling Mechanism for Light Field Statial Super-Resolution
<br>
<p align="center"> <img src="https://raw.github.com/YingqianWang/DistgSSR/master/Figs/DistgSSR.png" width="90%"> </p>

This is the PyTorch implementation of the spatial SR method in our paper "Disentangling Light Fields for Super-Resolution and Disparity Estimation". Please refer to our [paper](https://yingqianwang.github.io/) and [project page](https://yingqianwang.github.io/DistgLF) for details.<br>

## Preparation:
### Requirement:
* PyTorch 1.3.0, torchvision 0.4.1. The code is tested with python=3.6, cuda=9.0.
* Matlab for training/test data generation and performance evaluation.
### Datasets:
* We used the EPFL, HCInew, HCIold, INRIA and STFgantry datasets for training and test. Please first download our dataset via [Baidu Drive](https://pan.baidu.com/s/1mYQR6OBXoEKrOk0TjV85Yw) (key:7nzy) or [OneDrive](https://stuxidianeducn-my.sharepoint.com/:f:/g/personal/zyliang_stu_xidian_edu_cn/EpkUehGwOlFIuSSdadq9S4MBEeFkNGPD_DlzkBBmZaV_mA?e=FiUeiv), and place the 5 datasets to the folder `./Datasets/`.
### Generating training/test data:
* Run `Generate_Data_for_Train.m` to generate training data. The generated data will be saved in `./Data/train_kxSR_AxA/`.
* Run `Generate_Data_for_Test.m` to generate test data. The generated data will be saved in `./Data/test_kxSR_AxA/`.
### Download our pretrained models:
|  **Angular Resolution** | **Upscaling Factor** | **Channel Depth** | **Download Link** |
| :---------: |  :---------: | :----------: | :---------------: |
|   **5×5**   |   **2×SR**   |    **64**    | [**DistgSSR_5x5_2xSR.pth.tar**]() |
|   **5×5**   |   **4×SR**   |    **64**    | [**DistgSSR_5x5_4xSR.pth.tar**]() |
|     5×5     |     2×SR     |      32      | [DistgSSR_5x5_2xSR_C32.pth.tar]() |
|     5×5     |     4×SR     |      32      | [DistgSSR_5x5_4xSR_C32.pth.tar]() |
|     2×2     |     2×SR     |      64      | [DistgSSR_2x2_2xSR.pth.tar]() |
|     3×3     |     2×SR     |      64      | [DistgSSR_3x3_2xSR.pth.tar]() |
|     4×4     |     2×SR     |      64      | [DistgSSR_4x4_2xSR.pth.tar]() |
|     6×6     |     2×SR     |      64      | [DistgSSR_6x6_2xSR.pth.tar]() |
|     7×7     |     2×SR     |      64      | [DistgSSR_7x7_2xSR.pth.tar]() |
|     8×8     |     2×SR     |      64      | [DistgSSR_8x8_2xSR.pth.tar]() |
|     9×9     |     2×SR     |      64      | [DistgSSR_9x9_2xSR.pth.tar]() |



## Train:
* Set the hyper-parameters in `parse_args()` if needed. We have provided our default settings in the realeased codes.
* Run `train.py` to perform network training.
* Checkpoint will be saved to `./log/`.

## Test on the datasets:
* Run `test_on_dataset.py` to perform test on each dataset.
* The original result files and the metric scores will be saved to `./Results/`.

## Test on your own LFs:
* Place the input LFs into `./input` (see the attached examples).
* Run `demo_test.py` to perform spatial super-resolution. Note that, the selected pretrained model should match the input in terms of the angular resolution. 
* The super-resolved LF images will be automatically saved to `./output`.

## Results:

### Quantitative Results:
<p align="center"> <img src="https://raw.github.com/YingqianWang/DistgSSR/master/Figs/Metric-SSR.png" width="100%"> </p>

### Visual Comparisons:
<p align="center"> <img src="https://raw.github.com/YingqianWang/DistgSSR/master/Figs/Visual-SSR.png" width="100%"> </p>

### Efficiency:
<p align="center"> <img src="https://raw.github.com/YingqianWang/DistgSSR/master/Figs/Efficiency-SSR.png" width="50%"> </p>

### Angular Consistency:
<p align="center"> <a href="https://wyqdatabase.s3.us-west-1.amazonaws.com/DistgLF-SpatialSR.mp4"><img src="https://raw.github.com/YingqianWang/DistgSSR/master/Figs/AngCons-SSR.png" width="80%"></a> </p>


## Citiation
**If you find this work helpful, please consider citing:**
```
@Article{DistgLF,
    author    = {Wang, Yingqian and Wang, Longguang and Wu, Gaochang and Yang, Jungang and An, Wei and Yu, Jingyi and Guo, Yulan},
    title     = {Disentangling Light Fields for Super-Resolution and Disparity Estimation},
    journal   = {IEEE TPAMI (under review)}, 
    year      = {2022},   
}
```
<br>

## Contact
**Welcome to raise issues or email to [wangyingqian16@nudt.edu.cn](wangyingqian16@nudt.edu.cn) for any question regarding this work.**
