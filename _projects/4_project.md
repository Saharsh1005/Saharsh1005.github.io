---
layout: page
title: Tissue Segmentation
description: A vision transformer-based model uses the Coat architecture for binary FTU segmentation with an auxiliary loss for regularization.
img: assets/img/project_preview/hubmap_banner.jpg
importance: 2
category: AI
---

<!-- Add banner here -->
# HuBMAP + HPA: Functional Tissue Unit Segmentation <a name="project-title"></a>


<!-- Describe your project in brief -->
We have deveoped a **model to segment cell population neighborhoods** that perform an organs main function, also called as **Functional Tissue Units (FTU)** of 5 organs, namely: kidney, large intestine, lung, prostate and spleen. Here, we present a vision transformer-based approach using **Coat (Co-Scale Conv-Attentional Image Transformers) architecture** for binary FTU segmentation. We also implemented techniques like stain normalization, data augmentation and switched auxiliary loss for robust training which provided an improvement in accuracy of over 6%. Overall, our model achieved a **dice score** of **0.793** on the public dataset and **0.778** on the private dataset. The findings bolster the use of vision transformers-based models for dense prediction tasks. The study also assists in understanding the relationships between cell and tissue organization thereby providing a **comprehensive understanding of how cellular functions impact human health**.
