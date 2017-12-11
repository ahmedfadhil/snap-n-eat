# Snap & Eat (formerly deep139)
Deep Learning Hackathon 48h - Cotidiano (**First place Project =D** )

We believe nutrition tracking should be as simple as taking a picture.

Snap & Eat is a web application that tracks the user's food intake by pictures. We use state-of-the-art deep learning techniques to recognize dishes, making instant nutrition estimates from the user's meals.

The app also suggests meals based on the user's income, and is capable of showing places nearby that serve those dishes.

## Demo

![test](data/readme-imgs/app_homescreen.jpg) 
![test](data/readme-imgs/food_prediction.jpg)  

## Our model

We use an [Aggregated Residual Convolutional Neural Network](https://arxiv.org/abs/1611.05431) - ResNeXt-101 with 101 layers, pretrained on [ImageNet](http://www.image-net.org/) dataset. We finetune the model on [Food-101 dataset](https://www.vision.ee.ethz.ch/datasets_extra/food-101/), with more than 100 thousand images of 101 types of dishes. We achieve a significant improvement on accuracy (71% in our work compared to 50.1% in [Bossard et al., 2014](http://www.vision.ee.ethz.ch/~lbossard/bossard_eccv14_food-101.pdf)).

![test](data/readme-imgs/food101dataset.png) 

For recomending new dishes, we use minimum ditance in an n-dimensional space of nutritional information that describe each dish.

## Implementation

The system is implemented in Pytorch using [fastai lib](https://github.com/fastai/fastai), relying on Jupyter Notebooks for prototyping purposes. For the web app, we use Flask and Node.js.

## Instalation and usage

Dependencies:

- [fastai lib](https://github.com/fastai/fastai)
- Flask
- Node.js

# About the idea

According to the [World Health Organization](http://www.who.int/en/), worldwide obesity has nearly tripled since 1975. In the United States, almost 75% of the population is overweight and more than half of the population is obese ([OECD](http://www.oecd.org/)). Today, many diseases that were preivously thought as hereditary are now shown to be seen conected to biological disfunction related to nutrition.

Although being healty and eating better is something the vast majority of the population want, doing so usually requires great effort and organization. The lack of an easy and simple way to track nutrition information about the food you eat can easily lead to low engagement. By providing a very easy and fun way to keep track of what the user eat, we can largely improve engagement, and directly atack on of the largest health problems in the world.