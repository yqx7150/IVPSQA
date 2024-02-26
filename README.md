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
