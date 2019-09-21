# Kaggle-Aptos2019

My solution ranked 22th out of 2,943 on the [aptos2019-blindness-detection](https://www.kaggle.com/c/aptos2019-blindness-detection). 

1. **Preprocessing**

    I tried circle crop and Ben's Preprocessing. 
    But it didn't work.
    So finally the preprocessing did nothing.
    
    [Reference Notebook](https://www.kaggle.com/ratthachat/aptos-eye-preprocessing-in-diabetic-retinopathy). 
    

2. **Models and Input sizes**

    My final submission was a simple average of the three EfficientNetB5 models with different input sizes.
    Three input sizes 256, 328, and 456 were used.
    I wanted to try other models such as ResNets, 
    but I gave up because I only had kaggle's kernel as a computational resource.
    
    
3. **Augmentations**
    
    For augmentations, the following were helpful
    * flip vertical and horizontal,
    * max_rotate=180,
    * max_zoom=1.2,
    * brightness_range=0.2,
    * contrast_range=0.2.
    
    
4. **Training**
