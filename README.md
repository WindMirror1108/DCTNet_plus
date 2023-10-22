# DCTNet_plus:Salient Object Detection in RGB-D Videos

Code for paper, '**Salient Object Detection in RGB-D Videos**' 

[**Supplementary material** is also attached in the repo]


<p align="center">
    <img src="figures/Overview.png" width="100%" /> <br />
    <em> 
    Overview of DCTNet. (a) shows the big picture. (b) and (c) show the details of MAM and RFM, respectively. In the attention operations on the right-hand side in (c), since the coordinate attention and spatial attention processes are similar, the operations of spatial attention are represented in parentheses and are not repeated.
    </em>
</p>


## Downloads
1. **RDVS dataset.**
   - Full dataset with **realistic depth** (4.84G, 57 sequences): [Baidu Pan]()(fetch code: ) | [Google Drive]() (**Update link:**)
   - Full dataset with synthetic deptn (4.76G, 57 sequences): [Baidu Pan]()(fetch code: ) | [Google Drive]() (**Update link:**)
   - Training Set containing realistic and synthetic depth (2.56G, 32 sequences): [Baidu Pan]()(fetch code: ) | [Google Drive]() (**Update link:**)
   - Test Set containing realistic and synthetic depth (2.30G, 25 sequences): [Baidu Pan]()(fetch code: ) | [Google Drive]() (**Update link:**)
   - **Noting: realistic depth is in "/Depth" and synthetic depth is in "/SyntheticDepth"**
  

2. **DCTNet+ model.**
   - original model ckpt: [Baidu Pan](https://pan.baidu.com/s/1T_f_IPM9cJt4pzWbFTSgQQ?pwd=wm08)(fetch code: wm08) | [Google Drive]()
   - finetune on the test set of RDVS with **realistic depth**: [Baidu Pan](https://pan.baidu.com/s/1zSD_0ZyeSCedcyJcLX0G-w?pwd=wm08)(fetch code: wm08) | [Google Drive]()
   - finetune on the test set of RDVS with **synthetic depth**: [Baidu Pan](https://pan.baidu.com/s/1TpKoZULR-yuAeCvrNVoalg?pwd=wm08)(fetch code: wm08) | [Google Drive]()


3. **our training set and test set**
   - training set: [Baidu Pan]()(fetch code: ) | [Google Drive]()
   - test set: [Baidu Pan]()(fetch code: ) | [Google Drive]()



## Usage
1. Requirements
   - Python
   - PyTorch
   - Torchvision
   - Cuda

2. Training
   - Download the pre_trained ResNet34 backbone: [Baidu Pan]()(fetch code: ) | [Google Drive]() to './model/resnet/pre_train/'.
   - Download the train dataset (containing DAVIS16, DAVSOD, FBMS and DUTS-TR) from [Baidu Pan]()(fetch code: ) | [Google Drive]() and save it at './dataset/train/*'.
   - Download the pre_trained RGB, depth and flow stream models from [Baidu Pan]()(fetch code: ) | [Google Drive]() to './checkpoints/'
     - Noting: the pre_trained RGB should be saved at './checkpoints/spatial', pre_trained depth shoule be saved at './checkpoints/depth' and flow is same. 
   - The training of entire DCTNet is implemented on one NVIDIA RTX 3090 GPU.
     - run  `python train.py` in terminal
3. Testing
   - Download the test data (containing DAVIS16, DAVSOD, FBMS, SegTrack-V2, VOS) from  [Baidu Pan]()(fetch code: ) | [Google Drive]() and save it at './dataset/test/*'
   - Download the trained model from [Downloads](#downloads)(original model ckpt) and modify the  `model_path` to its saving path in the `test.py`.
   - Run `python test.py` in the terminal.
   - 

## VSOD
|**Year**|**Publisher**|**Paper**|**Model**|**RDVS**|**DAVIS**|**DAVSOD**|**FBMS**|**SegV2**|**ViSal**|**VOS**|
| :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
|2018|ECCV|[**PDB**](https://openaccess.thecvf.com/content_ECCV_2018/papers/Hongmei_Song_Pseudo_Pyramid_Deeper_ECCV_2018_paper.pdf)|[Code](https://github.com/shenjianbing/PDB-ConvLSTM)|[Baidu ](https://pan.baidu.com/s/1J7gUaAQhXxpF3Rd0jdrtQg?pwd=ef57)|[Baidu ]()|[Baidu ]()|[Baidu ]()|[Baidu ]()|[Baidu ]()|[Baidu ]()|
|2019 | ICCV | [**MGAN**](https://openaccess.thecvf.com/content_ICCV_2019/papers/Li_Motion_Guided_Attention_for_Video_Salient_Object_Detection_ICCV_2019_paper.pdf)|[Code](https://github.com/lhaof/Motion-Guided-Attention)|[Baidu ](https://pan.baidu.com/s/1qp6_wrPowCea-pNedtbNkg?pwd=rufu)|[Baidu ]()|[Baidu ]()|[Baidu ]()|[Baidu ]()|[Baidu ]()|[Baidu ]()|
|2019 | CVPR | [**SSAV**](https://openaccess.thecvf.com/content_CVPR_2019/papers/Fan_Shifting_More_Attention_to_Video_Salient_Object_Detection_CVPR_2019_paper.pdf)|[Code](https://github.com/DengPingFan/DAVSOD)|[Baidu](https://pan.baidu.com/s/1Rhjh0vvHqfqHpgC83-60XA?pwd=iq5g)|[Baidu]()|[Baidu]()|[Baidu]()|[Baidu]()|[Baidu]()|[Baidu]()|
|2020 | AAAI | [**PCSA**](https://aaai.org/papers/10869-pyramid-constrained-self-attention-network-for-fast-video-salient-object-detection/)|[Code](https://github.com/guyuchao/PyramidCSA)|[Baidu ](https://pan.baidu.com/s/1GbalsdHdQ75cfKSdSao5qA?pwd=rd09)|[Baidu ]()|[Baidu ]()|[Baidu ]()|[Baidu ]()|[Baidu ]()|[Baidu ]()|
|2021 | ICCV | [**FSNet**](https://openaccess.thecvf.com/content/ICCV2021/papers/Ji_Full-Duplex_Strategy_for_Video_Object_Segmentation_ICCV_2021_paper.pdf)|[Code](https://github.com/GewelsJI/FSNet)|[Baidu ](https://pan.baidu.com/s/1fYTZ6awbJNy-XHh_IWDk6g?pwd=9hie)|[Baidu ]()|[Baidu ]()|[Baidu ]()|[Baidu ]()|[Baidu ]()|[Baidu ]()|
|2021 | ICCV | [**DCFNet**](https://openaccess.thecvf.com/content/ICCV2021/papers/Zhang_Dynamic_Context-Sensitive_Filtering_Network_for_Video_Salient_Object_Detection_ICCV_2021_paper.pdf)|[Code](https://github.com/Roudgers/DCFNet)|[Baidu](https://pan.baidu.com/s/1zabfNUWB35z9FbpEjELYJA?pwd=hubj)|[Baidu ]()|[Baidu]()|[Baidu]()|[Baidu]()|[Baidu]()|[Baidu]()|
|2022 | ICIP | [**DCTNet**](https://arxiv.org/pdf/2202.06060.pdf)|[Code](https://github.com/luyukang/DCTNet)|[Baidu](https://pan.baidu.com/s/1VB0sJSUYxoUl__fQx8A-pA?pwd=yzd8)|[Baidu](https://pan.baidu.com/s/1S6n6aKaazrQ-w5BxD6rV9Q?pwd=awpg)|[Baidu](https://pan.baidu.com/s/1U4IazgOL-zcVM4JWqm4Odw?pwd=qmss)|[Baidu](https://pan.baidu.com/s/1Fw-UtU5A0815dfuRRB2OQw?pwd=sqxz)|[Baidu](https://pan.baidu.com/s/17Kx8qmJSeABkxE6dfxwngg?pwd=6rla)|[Baidu](https://pan.baidu.com/s/1dmRi_x96AoFzEFot6VRTHw?pwd=k7s5)|[Baidu](https://pan.baidu.com/s/1wBGiuW31MV-onMQeScmr2A?pwd=of9b)|


## RGB-D SOD
|**Year**|**Publisher**|**Paper**|**Model**|**RDVS**|
| :-: | :-: | :-: | :-: | :-: |
|2020 | ECCV | [**BBSNet**](https://arxiv.org/pdf/2007.02713.pdf)|[Code](https://github.com/DengPingFan/BBS-Net)|[Baidu ](https://pan.baidu.com/s/1eyMummax1HQpeI2CBrWZmA?pwd=obe0)| 
|2020 | CVPR | [**JLDCF**](https://openaccess.thecvf.com/content_CVPR_2020/papers/Fu_JL-DCF_Joint_Learning_and_Densely-Cooperative_Fusion_Framework_for_RGB-D_Salient_CVPR_2020_paper.pdf)|[Code](https://github.com/kerenfu/JLDCF)|[Baidu](https://pan.baidu.com/s/1kDOohakpxGwVRAv9qtDf5w?pwd=4bgi)
|2020 | CVPR | [**S2MA**](https://openaccess.thecvf.com/content_CVPR_2020/papers/Liu_Learning_Selective_Self-Mutual_Attention_for_RGB-D_Saliency_Detection_CVPR_2020_paper.pdf)|[Code](https://github.com/nnizhang/S2MAhttps://github.com/nnizhang/S2MA)|[Baidu](https://pan.baidu.com/s/1PxVWLhXL5VQjgQK-1toZtA?pwd=c3tf)
|2020 | ECCV | [**HDFNet**](https://arxiv.org/pdf/2007.06227.pdf)|[Code](https://github.com/lartpang/HDFNet)|[Baidu ](https://pan.baidu.com/s/1XlVARG4jUlbwW411IHq3ng?pwd=dgfi)
|2020 | TIP | [**DPANet**](https://ieeexplore.ieee.org/document/9247470)|[Code](https://github.com/JosephChenHub/DPANet)|[Baidu](https://pan.baidu.com/s/156frOJuJHqbkZVuYg0aybQ?pwd=ulh6)
|2021 | ICCV | [**SPNet**](https://openaccess.thecvf.com/content/ICCV2021/supplemental/Zhou_Specificity-Preserving_RGB-D_Saliency_ICCV_2021_supplemental.pdf)|[Code](https://github.com/taozh2017/SPNet)|[Baidu](https://pan.baidu.com/s/1RVdliC67daR_JJ44_-oYSQ?pwd=5rur)
|2021 | TIP | [**CDNet**](https://ieeexplore.ieee.org/document/9366409)|[Code](https://github.com/blanclist/CDNet)|[Baidu ](https://pan.baidu.com/s/1a-Eqeyf8Qvam81EZLw3Mtw?pwd=fvf1)
|2021 | CVPR | [**DCF**](https://openaccess.thecvf.com/content/CVPR2021/papers/Ji_Calibrated_RGB-D_Salient_Object_Detection_CVPR_2021_paper.pdf)|[Code](https://github.com/jiwei0921/DCF)|[Baidu ](https://pan.baidu.com/s/1O7heB5mgbgbMHz0pTOOFOA?pwd=aguk)
|2021 | ACM MM | [**TriTransNet**](https://arxiv.org/pdf/2108.03990.pdf)|[Code](https://github.com/liuzywen/TriTransNet)|[Baidu](https://pan.baidu.com/s/1AL1E8clMzPNek6kScyKzEw?pwd=svra)
|2021 | ICME | [**BTSNet**](https://arxiv.org/pdf/2104.01784.pdf)|[Code](https://github.com/zwbx/BTS-Net)|[Baidu](https://pan.baidu.com/s/1RgsWbFM2hutchErblTXJHQ?pwd=hi7x)
|2022 | TNNLS | [**RD3D**](https://ieeexplore.ieee.org/document/9889257)|Code|[Baidu](https://pan.baidu.com/s/1oLSu4jxZFaRDYeitAKJTYA?pwd=vwwf)

