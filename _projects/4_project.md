---
layout: page
title: Kaggle Hubmap Competition
description: A vision transformer-based model uses the Coat architecture for binary FTU segmentation with an auxiliary loss for regularization.
img: assets/img/project_preview/hubmap_banner.jpg
importance: 2
category: AI
---

<!-- Add banner here -->
![Banner2](/assets/img/project_preview/hubmap_banner.jpg)
# HuBMAP + HPA: Functional Tissue Unit Segmentation <a name="project-title"></a>

<!-- Add buttons here -->

![GitHub version](https://img.shields.io/static/v1?label=version&message=1.0&color=blue) ![GitHub last commit](https://img.shields.io/static/v1?label=last%20commit&message=oct%202022&color=red) ![GitHub issues](https://img.shields.io/static/v1?label=open%20issues&message=0&color=green)

<<<<<<< HEAD
<!-- Describe your project in brief -->
We have deveoped a **model to segment cell population neighborhoods** that perform an organs main function, also called as **Functional Tissue Units (FTU)** of 5 organs, namely: kidney, large intestine, lung, prostate and spleen. Here, we present a vision transformer-based approach using **Coat (Co-Scale Conv-Attentional Image Transformers) architecture** for binary FTU segmentation. We also implemented techniques like stain normalization, data augmentation and switched auxiliary loss for robust training which provided an improvement in accuracy of over 6%. Overall, our model achieved a **dice score** of **0.793** on the public dataset and **0.778** on the private dataset. The findings bolster the use of vision transformers-based models for dense prediction tasks. The study also assists in understanding the relationships between cell and tissue organization thereby providing a **comprehensive understanding of how cellular functions impact human health**.

## Table of contents

- [Project Title](#project-title)
- [Table of contents](#table-of-contents)
- [Set Up Environment](#setupenv)
- [Repository Structure](#repostr)
- [Running the Code](#runcode)
    - [Training](#train)
    - [Inference](#infer)
- [Predictions](#predictions)
- [Results](#result)
- [Dataset](#dataset)
- [Citation](#cite)
- [Authors](#authors)
- [License](#license)

## Set Up Environment <a name="setupenv"></a>
1. Set up a new conda environment and activate it.
   ```bash
   # Create an environment with Python 3.7.2.
   conda create -n hubmap python==3.7.2
   conda activate hubmap
   # OR
   conda env create -f environment.yml
   conda activate hubmap
   ```

2. Install required packages.
   ```bash
   albumentations==1.1.0
   colorama==0.4.5
   einops==0.4.1
   imagecodecs==2022.9.26
   matplotlib==3.5.2
   numpy==1.23.1
   opencv_python_headless==4.6.0.66
   pandas==1.4.3
   Pillow==9.2.0
   scikit_image==0.19.3
   scikit_learn==1.1.2
   skimage==0.0
   spams==2.6.5.4
   spams_bin==2.6.4
   tabulate==0.8.10
   tifffile==2022.5.4
   timm==0.4.12
   torch==1.12.1
   torchmetrics==0.9.3
   torchvision==0.13.1
   tqdm==4.64.0
   transformers==4.21.1
   ```

## Repository Structure <a name="repostr"></a>
Below are the main directories in the repository: 

- `data/`: images and masks for model training (download from kaggle competitions) and test image for inference along with metadata .csv files.
- `docs/`: figures used in this repo

Below are the main modules in the repository:
- `coat.py`: defines coat architecture
- `mit.py`: defines mit architecture
- `pvt_v2.py`: defines pvt_v2 architecture
- `daformer.py`: defines daformer architecture

Below are the models implemented  in the repository:
- `model_coat_daformer.py`: model definition with hyperparameter setting.
	- encoder: coat_small_parallel_plus
	- decoder: daformer_conv_1x1  
- `model_mit_segformer.py`: model definition with hyperparameter setting.
	- encoder: mit-b2
	- decoder: daformer_conv_1x1  
- `model_pvt_v2_daformer.py`: model definition with hyperparameter setting.
	- encoder: pvt_v2_b4
	- decoder: daformer_conv_3x3

Below are the main executable scripts in the repository:

- `train.py`: main training script
- `inference.py`: main inference script for FTU segmentation. Outputs: RLE prediction along with image and prediction overlay.

## Running the Code <a name="runcode"></a>

### Training <a name="train"></a>

a. Before training setup up the configuration as follows:

- **model configs:**
	- model_parameters_list: 
		- module = provide the model file name
		- params =  set encoder and decoder based on the model 
		- checkpoint =  Imagenet pretrained weights from `/pretrained_weights` 

- **directory config**
	- img_size: size of image (768x768)
	- root_dir: path to dataset directory
	- IMAGES: train images directory
	- MASKS: train masks directory
	- stain_norm_path: target image for stain normalization
	- kaggle: flag to run on kaggle (bool)

- **data config**
	- batch_size: batchesize while training (2,4,8)
	- debug: flag for debugging (bool)
	num_workers: for dataloader

- **optimizer config**
	- epochs: number of training epochs
	- lr: learning rate
	- optimizer: Adam or AdamW

- **scheduler config**
	- scheduler: ReduceLROnPlateau or CosineAnnealingLR
	- min_lr: min. learning rate
	- wd: weight decay
	- lr_drop: for stepLR (optional)

b. Run `train.py`

### Inference <a name="infer"></a>

a. Before inference setup up the configuration as follows:

- **model configs:**

	- model_parameters_list: 
		- module = provide the model file name
		- params =  set encoder and decoder based on the trained model 
		- checkpoint =  trained model weights from: `/weights` 
		
- **directory config**
	- img_size: size of image (768x768)
	- root_dir: path to root directory containing inference data `./data`
	- stain_norm_path: target image for stain normalization `./data/stain_target`
	- kaggle: flag to run on kaggle (bool)

- **threshold**
	- thr: (dict) provide threshold as a nested dict based on dataset and organ

b. Run `inference.py`

## Sample Predictions <a name="predictions"></a>
Below is a sample prediction generated using the CoaT model:
![Prediction](/assets/img/project_preview/hubmap_result.jpg)

## Results <a name="result"></a>
Kaggle Competition results: 

**CoaT model**

| Data  |  Dice Score |
| ------------ | ------------ |
| Public  | 0.79321  |
| Private | 0.77805 |

Kaggle Competition Bronze medal🥉. Finishing in top 8%.
![LB](/assets/img/project_preview/hubmap_kaggle_result.jpg)

## Dataset <a name="dataset"></a>
The original HubMap + HPA: Hacking the Human Body kaggle dataset can be found [here](https://www.kaggle.com/competitions/hubmap-organ-segmentation/data "here").

## References <a name="cite"></a>

- CoaT: https://arxiv.org/abs/2104.06399
- PVTv2: https://arxiv.org/abs/2106.13797
- Segformer: https://arxiv.org/abs/2105.15203
- StainTools: https://github.com/Peter554/StainTools
- Daformer: https://arxiv.org/abs/2111.14887
- HubMap + HPA competition: https://www.kaggle.com/competitions/hubmap-organ-segmentation
- Special thanks to Hengck for informative kaggle discussions, I learned a lot!

## Authors  <a name="authors"></a>
- Saharsh Barve

## License <a name="license"></a>
[(Back to top)](#table-of-contents)

Note: The SegFormer model is licensed under Apache2.0, therefore the derived weights for Segformer-mit-b2 are also shared under the same license. Please consider the implications of using the weights under this license on your work and its licensing.
=======
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/1.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/3.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>

You can also put regular text between your rows of images.
Say you wanted to write a little bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, _bled_ for your project, and then... you reveal its glory in the next row of images.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>

The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

{% raw %}

```html
<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
```

{% endraw %}
>>>>>>> 0af4aecf50426fc1e35696ca4c47940737175b26
