# BoneMarrow
**Abstract**  
Bone marrow examination is an essential step in both diagnosing and managing hematologic disorders. However, challenges to perform bone marrow analysis on whole-slide images (WSIs) include large dimensions of data to process, numerous cell types to identify and small inter-class difference within a maturation stage among various cell types. To the authors' best knowledge, this is the first study on fully automatic bone marrow analysis using WSIs. In this study, we develop an efficient and fully automatic hierarchical deep learning framework for bone marrow WSI analysis in seconds. The proposed hierarchical framework consists of (1) a deep learning model for rapid localization of bone marrow particles and cellular trails generating regions of interest for further analysis, (2) a patch-based deep learning model for cell identification of 15 cell types, ncluding myeloid series, erythroid series and lymphoid series, and (3) a fast stitching model for integrating patch-based results and producing final outputs. In evaluation, the proposed method achieves high recall, accuracy and the area under the precision-recall curve (PR-AUC) metrics of 0.959, 0.992 and 0.972, respectively, and takes only 43 seconds to perform bone marrow analysis for a WSI. In comparison with the small-image-based benchmark methods, the proposed method demonstrates superior performance in recall, accuracy, PR-AUC and computational time. The proposed fully automatic method is demonstrated to be effective and efficient in bone marrow cell analysis of WSIs for routine clinical usage.

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
This extension to the Caffe library is released under a creative commons license which allows for personal and research use only. For a commercial license please contact the authors. You can view a license summary here:  
http://creativecommons.org/licenses/by-nc/4.0/
