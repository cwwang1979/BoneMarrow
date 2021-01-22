# BoneMarrow

## Publications
If you use this software in your research, please cite our publication:  
  
Ching-Wei Wang, Sheng-Chuan Huang, Yu-Ching Lee, Yu-Jie Shen, Shwu-Ing Meng and Jeff L Gaol. "Deep Learning for Bone Marrow Cell Detection and Classification on Whole-Slide Images." Medical Image Analysis (under review). 


## Cloud Demo
AI inference process and results are shown in the [video](https://drive.google.com/file/d/1-qkil0xDLDo30YNlEiOTp1xDQ77uSipf/view?usp=sharing).

#### Device specifications
- **CPU:** Intel Xeon Gold 6148
- **RAM:** 512 GB
- **GPU:** NVIDIA TITAN RTX 24 GB * 4

#### Time consumption
- **Data extraction time:** 42 seconds
- **AI Inference time:** 42 seconds

In the cloud demo, the system gets a WSI file from the remote NAS, so data extraction time takes more than the workstation demo.


## Workstation Demo
AI inference process and results as follows:   
##### ![result](result_screenshot.png)

#### Device specifications
- **CPU:** Intel Core i9-7900X
- **RAM:** 128 GB
- **GPU:** NVIDIA GeForce GTX 1080 Ti 11 GB * 2

#### Time consumption
- **Data extraction time:** 6 seconds
- **AI Inference time:** 92 seconds

In the workstation demo, the WSI file is stored locally, so data extraction time takes less than the cloud demo.


## Setup

#### Requirerements
- ubuntu 18.04
- RAM >= 16 GB
- GPU Memory >= 6 GB
- GPU driver version >= 410.48
- CUDA version >= 10.0
- cuDNN version >= 7.4.2

#### Download
Execution file, configuration file, and models are download from the [zip](https://drive.google.com/file/d/18fGMoaZSL8J0Wu63gKZRFKGEtlhRZ-Ch/view?usp=sharing) file.  
The demo data is [here](https://drive.google.com/file/d/1-g-FOBLqyhsjwBQCVsQ3WlAwQmBpvHV9/view?usp=sharing).

#### File structure
```
BoneMarrow/
│
├── BoneMarrow - execution file
├── gpu_setting.json - configuration file
│
├── TestImgTemp/ - temp data extraction folder
|
├── Data/ - inference data location
│   ├── 1M14.mrxs
│   └── 1M14/
│       ├── Index.dat
│       ├── Slidedat.ini
│       ├── Data0000.dat
│       ├── Data0001.dat
│       ├── Data0002.dat
│       ├── Data0003.dat
│       ├── Data0004.dat
│       │       ⋮
│       └── Data0035.dat
│
├── Model/ - contains detection models
|   ├── 27_BOOST_POSITIVE_i70w
|   └── NTU_ROI_i10w
|
└── Result/ - inference result is saved here

```

#### Inference
Open the gpu_setting.json file set the GPUs used, the file format as follows:  
```
[0, 1]	//number of GPUs to use for testing.
```

Then in a terminal run:  
```
./BoneMarrow
```


## License
This extension to the Caffe library is released under a creative commons license, which allows for personal and research use only. For a commercial license please contact Prof Ching-Wei Wang. You can view a license summary here:  
http://creativecommons.org/licenses/by-nc/4.0/


## Contact
Prof. Ching-Wei Wang  
  
cweiwang@mail.ntust.edu.tw; cwwang1979@gmail.com  
  
National Taiwan University of Science and Technology
