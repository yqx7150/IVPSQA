# IVPSQA    
Invertible and Variable Augmented Network for Pretreatment Patient-Specific Quality Assurance Dose Prediction      
Z. Zou, C. Gong, L. Zeng, Y. Guan, B. Huang, X. Yu, Q. Liu, M. Zhang     
Journal of Imaging Informatics in Medicine, 1-12, 2024.    
https://link.springer.com/article/10.1007/s10278-023-00930-w     


#========================train=========================
#DATA
Prepare your own datasets for IVPSQA

You need to create at least two modality medical images from domain A /data/A and from domain B /data/B. Then you can train the model with the dataset flag --root1 './data/A' --root2 './data/B'. Optionally, you can create hold-out test datasets at ./data/A_test and ./data/B_test to test your model.

##  1to1---RTDose

python train.py --task=1to1 --out_path="./exps/"

##  2to1---RTDose+CT

python train.py --task=2to1 --out_path="./exps/"

##  resume training:

To fine-tune a pre-trained model, or resume the previous training, use the --resume flag


#========================test==========================

python test.py --task=2to1 --out_path="./exps/" --ckpt="./exps/2to1/checkpoint/latest.pth"

python test.py --task=1to1 --out_path="./exps/" --ckpt="./exps/1to1/checkpoint/latest.pth"


## The training and testing pipeline of IVPSQA
<div align="center"><img src="https://github.com/yqx7150/IVPSQA/blob/main/fig2.png"> </div>
    
## A: Illustration of two different input modes of IVPSQA; B: The detailed architecture of IVPSQA
<div align="center"><img src="https://github.com/yqx7150/IVPSQA/blob/main/fig3.png"> </div>

## Visualization results of several comparison methods
<div align="center"><img src="https://github.com/yqx7150/IVPSQA/blob/main/fig4.png"> </div>

### Other Related Projects

  * Variable Augmented Network for Invertible Modality Synthesis and Fusion  [<font size=5>**[Paper]**</font>](https://ieeexplore.ieee.org/abstract/document/10070774)   [<font size=5>**[Code]**</font>](https://github.com/yqx7150/iVAN)    
  
 * Variable augmentation network for invertible MR coil compression  [<font size=5>**[Paper]**</font>](https://www.sciencedirect.com/science/article/abs/pii/S0730725X24000225)   [<font size=5>**[Code]**</font>](https://github.com/yqx7150/VAN-ICC)         

 * Virtual coil augmentation for MR coil extrapoltion via deep learning  [<font size=5>**[Paper]**</font>](https://www.sciencedirect.com/science/article/abs/pii/S0730725X22001722)   [<font size=5>**[Code]**</font>](https://github.com/yqx7150/VCA)    

  * Variable Augmented Network for Invertible Decolorization (基于辅助变量增强的可逆彩色图像灰度化)  [<font size=5>**[Paper]**</font>](https://jeit.ac.cn/cn/article/doi/10.11999/JEIT221205?viewType=HTML)   [<font size=5>**[Code]**</font>](https://github.com/yqx7150/VA-IDN)        

  * Synthetic CT Generation via Invertible Network for All-digital Brain PET Attenuation Correction  [<font size=5>**[Paper]**</font>](https://arxiv.org/abs/2310.01885)   [<font size=5>**[Code]**</font>](https://github.com/yqx7150/PET_AC_sCT)        
    
  * Variable augmented neural network for decolorization and multi-exposure fusion [<font size=5>**[Paper]**</font>](https://www.sciencedirect.com/science/article/abs/pii/S1566253517305298)   [<font size=5>**[Code]**</font>](https://github.com/yqx7150/DecolorNet_FusionNet_code)   [<font size=5>**[Slide]**</font>](https://github.com/yqx7150/EDAEPRec/tree/master/Slide)   
   








