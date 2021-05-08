# SD2GAN
SD2GAN: A Siamese Dual Discriminator Generative Adversarial Network for Mode Collapse Reduction. 

This project implements the SD2GAN algorithm, presented in this [preprint paper](https://www.researchgate.net/publication/350109061_SD2GAN_A_Siamese_Dual_Discriminator_Generative_Adversarial_Network_for_Mode_Collapse_Reduction). 

# Contributers:
[Manal Allahyani](https://github.com/imnawar), [Rahaf Alsulami](https://github.com/rahafalsulami), [Taif Alwafi](https://github.com/TaifAlwafi), Tarik Alafif, Heyfa Ammar, [Sari Sabban](https://github.com/sarisabban), Xuewen Chen

# Description:
This repo contains an example notebook with a TensorFlow implementation of SD2GAN on MNIST and Fashion-MNIST datasets.

# Prerequisites
- Python 3.6+
- Tensorflow 2.0+

# Usage 
open SD2GAN.ipynb then, 
- To use the pretrained model check on parameters and make sure the ```train``` otption is set to False
```
params = {
    'dataset': "mnist", # 'mnist' , 'fashion'
    'train' : False, 
    'pretrained': "SD2GAN", 
    'z_dim' : 100, 
    'lr' : 0.0001, 
    'lr_disc2' : 0.00009, 
    'beta' : 0.5, 
    'bs' : 32, 
    'epochs' : 30000
}
```
- To train SD2GAN make sure the ```train``` otption is set to True
```
params = {
    'dataset': "mnist", # 'mnist' , 'fashion'
    'train' : True, 
    'pretrained': "SD2GAN", 
    'z_dim' : 100, 
    'lr' : 0.0001, 
    'lr_disc2' : 0.00009, 
    'beta' : 0.5, 
    'bs' : 32, 
    'epochs' : 30000
}
```
