The goal was to train a model to segment diseases on plant leaves. At first, I used a standard U-Net architecture with DiceLoss, but the model plateaued around a Dice score of 0.4.

I started blindly tweaking parameters and switched to a pretrained ResNet34 as the encoder. That helped a bit, but still wasn’t enough to beat the competition baseline.

Eventually, I realized the major issue was with tiny affected areas. Inspired by this article: Leaf Disease Segmentation using DeepLabV3, I switched to a heavier pretrained model and changed the loss function. Later, I updated the loss again to better handle small objects.

Throughout this process, I kept improving the augmentations, and also tried different optimizers hoping to escape the plateau.

The model trained for about 30 epochs before giving satisfying results. Since I lack experience in some basic things, I spent a few extra hours figuring out how to generate a valid submission.

Unlike situations where I have no clue what's going on, here I actually had a decent understanding and managed to experiment with different hyperparameters and architectures.

Overall, I found the task not too difficult, with a well-balanced time window and an interesting technical challenge. I’m confident that continuing training with the current setup would yield even better results.