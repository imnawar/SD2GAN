# SD2GAN
SD2GAN: A Siamese Dual Discriminator Generative Adversarial Network for Mode Collapse Reduction. 

This project implements the SD2GAN algorithm, presented in this [preprint paper](https://www.researchgate.net/publication/350109061_SD2GAN_A_Siamese_Dual_Discriminator_Generative_Adversarial_Network_for_Mode_Collapse_Reduction). 

# Contributers:
[Manal Allahyani](https://github.com/imnawar), [Rahaf Alsulami](https://github.com/rahafalsulami), [Taif Alwafi](https://github.com/TaifAlwafi), Tarik Alafif, Heyfa Ammar, [Sari Sabban](https://github.com/sarisabban), Xuewen Chen

# Description:
This repo contains an example notebook with a TensorFlow implementation of SD2GAN on MNIST and Fashion-MNIST datasets.

SD2GAN combined a diversity network, which consisted of a Siamese Network and an additional discriminator with the regular GANs' architecture. SD2GAN architecture illustrated in this figure: 

![SD2GAN](https://user-images.githubusercontent.com/36853625/117652573-04e40900-b19c-11eb-9811-a70ab4c95087.png)

The Siamese nwtwork used to measure the similarity in batch of data, we used the following architecture of the Siamese network:

![SNN](https://user-images.githubusercontent.com/36853625/117653385-ff3af300-b19c-11eb-95f1-991fa8262f59.png)


# Algorithm 
The Algorithm used in SD2GAN training is described as follows: 

![sd2gan_Algorithm ](https://user-images.githubusercontent.com/36853625/117651585-c568ed00-b19a-11eb-973f-23b539f3eba1.png)

The result of this algorithm is get an efficient generator that produces diverse and realistic data. To achive this, there are other components that should be included in the algorithm steps such as the Siamese network, discriminator2 and discriminator1. Each component has its own inputs and outputs and all of them contributed to generator training.

Starting with the Siamese network trainig, the training set of Siamese should be integrated by training dataset and the noise set produced by generator before its training which is similar to that produced by the beginning of its training. This resulted in get an efficient Siamese network that can discover the similarity between the real data and the generated data during the other components training loop.

# Prerequisites
- Python 3.6+
- Tensorflow 2.0+

# Train SN with SD2GAN

# Ues the pre-trained SN 
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
