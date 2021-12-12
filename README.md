## DistgSSR: Disentangling Mechanism for Light Field Statial Super-Resolution
<br>
<p align="center"> <img src="https://raw.github.com/YingqianWang/DistgSSR/master/Figs/DistgSSR.png" width="90%"> </p>

**This is the PyTorch implementation of the spatial SR method in our paper "*Disentangling Light Fields for Super-Resolution and Disparity Estimation*". Please refer to our [paper](https://yingqianwang.github.io/) and [project page](https://yingqianwang.github.io/DistgLF) for details.**<br>

## Download our SR results:
We share the super-resolved LF images generated by our DistgSSR on all the 5 datasets for both 2x and 4x SR. With our provided results, researchers can compare their algorithms to our DistgSSR without running our method. The original results can be download [here]().

## Requirement:
* PyTorch 1.3.0, torchvision 0.4.1. The code is tested with python=3.6, cuda=9.0.
* Matlab for training/test data generation and performance evaluation.

## Perform a demo inference:
Run `test.py` to perform a demo inference. Note that, the selected pretrained model should match the generated input data and the preset network architecture. Results will be saved to `./output`.

## Datasets and preparation:
* We used the EPFL, HCInew, HCIold, INRIA and STFgantry datasets for training and test. Please first download our dataset via [Baidu Drive](https://pan.baidu.com/s/1mYQR6OBXoEKrOk0TjV85Yw) (key:7nzy) or [OneDrive](https://stuxidianeducn-my.sharepoint.com/:f:/g/personal/zyliang_stu_xidian_edu_cn/EpkUehGwOlFIuSSdadq9S4MBEeFkNGPD_DlzkBBmZaV_mA?e=FiUeiv), and place the 5 datasets to the folder `./Datasets/`.
* Run `Generate_Data_for_Train.m` to generate training data. The generated data will be saved in `./Data/train_kxSR_AxA/`.
* Run `Generate_Data_for_Test.m` to generate test data. The generated data will be saved in `./Data/test_kxSR_AxA/`.

## Train:
* Set the hyper-parameters in `parse_args()` if needed. We have provided our default settings in the realeased codes.
* Run `train.py` to perform network training.
* Checkpoint will be saved to `./log/`.

## Test:
* Run `test.py` to perform test on each dataset.
* The PSNR and SSIM values of each dataset will be saved to `./log/`.

## Results:

### Quantitative Results:
<p align="center"> <img src="https://raw.github.com/YingqianWang/DistgSSR/master/Figs/Metric-SSR.png" width="100%"> </p>

### Visual Comparisons:
<p align="center"> <img src="https://raw.github.com/YingqianWang/DistgSSR/master/Figs/Visual-SSR.png" width="100%"> </p>

### Efficiency:
<p align="center"> <img src="https://raw.github.com/YingqianWang/DistgSSR/master/Figs/Efficiency-SSR.png" width="60%"> </p>

### Performance w.r.t. Angular Resolution:
<p align="center"> <img src="https://raw.github.com/YingqianWang/DistgSSR/master/Figs/AblationSSR-AngRes.png" width="60%"> </p>

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
