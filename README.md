﻿## __Comparison of Vision Transformer (ViT) and MLP-Mixer__

 This is conducted on CIFAR10 dataset with $60,000$ images of $32 \times 32$ size in $10$ classes with $6000$ images per class.

We have divided training images set into $45,000$ for training, $5000$ for validation, before testing on $10,000$ images in test set.

- Data Transformation implemented on Training + Validation set : 
Horizontal Flip, Resized Crop, and Normalization
- Data Transformation implemented on Test : Normalization.

---
__Vision Transformer (ViT)__ 

Attention Block in ViT is modelled with embedding size of 256, hidden dimension of 512, and 8 heads in Multi-head Attention block before being passed onto Transformer.

__MLP-Mixer__ 

Two MLP Heads were added into one MLP-Mixer block. MLP head had hidden dimension of 512, and token and channel MLP dimension as 256, and 1024, respectively.

---

We have then conducted our experiment with three uniformity across both model of __ViT__ and __MLP-Mixer__:
- ``learning_rate = 2e-4`` ``num_epochs = 30`` and ``dropout=0.2``

Our best results for both models are given below:

| Model Name | Training Parameters | Training Time | Learning Rate | No. Epochs | Training Accuracy | Validation Accuracy | MODEL ACCURACY|
|-------|------|--------|---------|--------|-------|-------|---------|
|__ViT__ | 3,195,146 | 6:00 Hr | 2e-4 | 30 |61.85 | 59.36 | 58.71|
| __MLP-Mixer__ |  __1, 116, 490__ | __1:48 Hr__ | 2e-4 | 30 | __70.80__  | __68.64__ | __68.32__|


We can clearly observe, with less than one-third of parameters and training time, __MLP-Mixer is clearly a winner over ViT__ for better training accuracy(& validation), and model accuracy.


__Note:__

We ran our models with $30$ epochs, so both model still had time to convergence to their best, as loss and accuracy were not flattened for both. However, results would have been fully congruent to our conclusion

- Vit Model's Loss and Accuracy Plot
![Plot](Plot_num_ep_30_lr2e-4.png)

- MLP-Mixer's Loss and Accuracy Plot 

![Plot](MLP-Mixer_Loss_Acc_lr2e-4.png)

