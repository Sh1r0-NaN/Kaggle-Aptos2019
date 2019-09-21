# Kaggle-Aptos2019

My solution ranked 22th out of 2,943 on the [aptos2019-blindness-detection](https://www.kaggle.com/c/aptos2019-blindness-detection).


1. **Preprocessing**

    I tried circle crop and Ben's Preprocessing. 
    But it didn't work.
    So finally the preprocessing did nothing.
    
    [Reference kernel](https://www.kaggle.com/ratthachat/aptos-eye-preprocessing-in-diabetic-retinopathy). 
    

2. **Models and Input sizes**

    My final submission was a simple average of the three EfficientNetB5 models with different input sizes.
    Three input sizes 256, 328, and 456 were used.
    I wanted to try other models such as ResNets, 
    but I gave up because I only had kaggle's kernel as a computational resource.
    
    
3. **Augmentations**
    
    The following was used as data ugmentations.
    * flip vertical and horizontal
    * max_rotate=180
    * max_zoom=1.2
    * brightness_range=0.2
    * contrast_range=0.2
    
    
4. **Training and Testing**

    For the training, I referred to the public kernel(https://www.kaggle.com/drhabib/starter-kernel-for-0-79).
    First, 2015 training data was used for pretrain. 
    After that, I trained with data from blend 2015 and current competition.
    
    Finally, TTA(only flip vertical and horizontal) was performed on each model, and the final result was an ensemble of these.
    
    The single score for each model and ensemble score is shown below.
    * EfficientNet-B5, input size 256 Public : 0.796934, Private : 0.916653
    * EfficientNet-B5, input size 328 Public : 0.800294, Private : 0.921412
    * EfficientNet-B5, input size 456 Public : 0.801565, Private : 0.919786
    * Ensemble models, Public : 0.815499, Private : 0.929032
