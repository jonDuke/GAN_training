# CIFAR10 GAN

This folder contains everything related to the CIFAR10 GAN I explored.  This was the first project in this repository.

To start with, I followed the tutorial [found here](https://machinelearningmastery.com/how-to-develop-a-generative-adversarial-network-for-a-cifar-10-small-object-photographs-from-scratch/).  Thanks to Jason Brownlee for writing it!

## What is CIFAR10?

[CIFAR-10](https://en.wikipedia.org/wiki/CIFAR-10) is a dataset originally published by the Canadian Institute for Advanced Research (hence CIFAR).  It was meant to be used for computer vision projects, specifically image classification.  It contains 60000 images split among 10 different classes such as planes, trucks, cats, etc.  Those are split 50k/10k into training and test sets.  The images are all very small, only 32x32 pixels, which means any models trained with it can finish relatively quick.

For this project, we didn't care as much what the labels were.  Instead I simply trained a GAN on the images, and once trained it could randomly generate similar ones.

## Initial results

Following the turorial, I trained a GAN on the entire 50k training set of images.  Right away, it was able to generate images with distinctive features, even if they were still mostly a jumble of colors.  Here's an example after only 10 training epochs: ![Example after 10 epochs](https://github.com/jonDuke/GAN_training/blob/main/CIFAR10/Images/generated_plot_e010.png?raw=true)

Of course I didn't stop there.  After a little over 2 hours of training (200 epochs), I got this output instead: ![Example after 200 epochs](https://github.com/jonDuke/GAN_training/blob/main/CIFAR10/Images/generated_plot_e200.png?raw=true)

I know what you're thinking, those images aren't too impressive either.  But they do show a lot of distinct features and you can usually tell what kind of image it was trying to generate.

the weights for the final trained model are available [here](https://github.com/jonDuke/GAN_training/blob/main/CIFAR10/Models/generator_model_200.h5) in this folder, in case you want to try loading it yourself.  That'll save you the time of training it.

## Next steps

I plan to try tweaking some things myself, which will end up in a new notebook here later.

- There's no reason to leave out the 10k images in the test set.  I can add those in.
- I think I might also be able to get better results by training only on a single class of image, like cats for example.  This will greatly reduce the number of images to train on, but they will be similar.  Will this work better?


