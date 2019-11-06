some more hot-sauce?
- add a section on how to import dependancies using the txt file? 

-After figuring out Transfer Learning with VGG16:
    - Extensions:
    
            - [x] Tune Learning Rate
                - Adam optimization instead of stochastic gradient descent
                
            - [x] Regularaize Transfer Learning Model
                - early stopping
                
            - Test Time Automation


## Adam Optimizer
    - an extension of stochastic gradient descent
    - Adam is not an acronym and not spelled ADAM! The name is derived from **adaptive moment estimation**

## Early Stopping  
    - a type of callback 
    - https://keras.io/callbacks/
    - Problem: how many epochs to train for to avoid overfitting but train enough to avoid underfitting?
        - we can monitor performance during training, create and configure Early Stopping using model checkpoint callbacks
     



|model                             | # Epochs | wall time |CPU or GPU | fBeta |
|:---------------------:           |:--------:|:---------:| :-------: | :----:|
|Baseline                          |    50    | 3h 17min  | CPU       | 0.830 |
|Baseline + Dropout Regularization |    100   | 9h 13min  | CPU       | 0.847 |
|Baseline + Dropout Regularization |    100   | 0h 36min  | GPU p100  | 0.845 |
|Baseline + Image Data Augmentation|    200   | 4h 56min  | GPU p100  | 0.879 |
|Transfer Learning                 |    20    | 4h 56min  | GPU v100  | 0.859 |
|TransferLearning+FineTuning+<br>ImageDataAugmentation| 30 | hr min  |GPU V100 |fbeta|
|TransferLearning+FineTuning+<br>ImageDataAugmentation+<br>EarlyStopping|12| 7hr 37min | GPU v100 |0.896| 
|TransferLearning+FineTuning+<br>ImageDataAugmentation+<br>Adam Optimizer| 30 | 0hr 43min  |GPU V100 |0.883|

