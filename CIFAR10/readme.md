# CIFAR10 GAN

This folder contains everything related to the CIFAR10 GAN I explored.  This was the first project in this repository.

To start with, I followed the tutorial [found here](https://machinelearningmastery.com/how-to-develop-a-generative-adversarial-network-for-a-cifar-10-small-object-photographs-from-scratch/).  Thanks to Jason Brownlee for writing it!

For a more in-depth explanation of the technical bits, and why the GAN was designed how it is, I recommend reading that original tutorial.

## What is CIFAR10?

[CIFAR-10](https://en.wikipedia.org/wiki/CIFAR-10) is a dataset originally published by the Canadian Institute for Advanced Research (hence CIFAR).  It was meant to be used for computer vision projects, specifically image classification.  It contains 60000 images split among 10 different classes such as planes, trucks, cats, etc.  Those are split 50k/10k into training and test sets.  The images are all very small, only 32x32 pixels, which means any models trained with it can finish relatively quick.

Here's an example of the images in it:

![CIFAR10 example](https://github.com/jonDuke/GAN_training/blob/main/CIFAR10/Images/CIFAR10_example.png?raw=true)

For this project, we didn't care as much what the class labels were.  Instead I simply trained a GAN on the images, and once trained it could randomly generate similar ones.

## Initial results

Following the turorial, I trained a GAN on the entire 50k training set of images.  Right away, it was able to generate images with distinctive features, even if they were still mostly a jumble of colors.  Here's an example after only 10 training epochs:

![Example after 10 epochs](https://github.com/jonDuke/GAN_training/blob/main/CIFAR10/Images/generated_plot_e010.png?raw=true)

Of course I didn't stop there.  After a little over 2 hours of training (200 epochs), I got this output instead:

![Example after 200 epochs](https://github.com/jonDuke/GAN_training/blob/main/CIFAR10/Images/generated_plot_e200.png?raw=true)

I know what you're thinking, those images aren't too impressive either.  But they do show a lot of distinct features and you can usually tell what kind of image it was trying to generate.

the weights for the final trained model are available [here](https://github.com/jonDuke/GAN_training/blob/main/CIFAR10/Models/generator_model_200.h5) in this folder, in case you want to try loading it yourself.  That'll save you the time of training it.

## Further exploration

One of the first questions I asked myself here is "would this get better results if I only trained on one kind of picture?  So the second notebook here is my attempt at following that.  I arbitrarily decided to use pictures of cats, but it would be easy to re-run the notebook with a different class.

The dataset was evenly distributed among 10 classes, so even after combining the test and train sets that means I only have 6000 images for each one.  Now that's a fairly large number, but nowhere near the 50k the first model was trained with.  To compensate, I let this one train for 2000 epochs instead of 200.  Otherwise, I made no other changes to the model structure so I could see how performance changed after just the dataset change.

Initial results were predictably a fuzzy mess.  Even after the first 100 epochs, I only got this output:

![Example after 100 epochs](https://github.com/jonDuke/GAN_training/blob/main/CIFAR10/Images/cat_generated_plot_e100.png?raw=true)

Halfway through, at 1000 epochs, we start getting some more promising results.  You can clearly see the cat shapes in these ones.

![Example after 1000 epochs](https://github.com/jonDuke/GAN_training/blob/main/CIFAR10/Images/cat_generated_plot_e1000.png?raw=true)

However, quality never seemed to get much better than that.  The final example saved at 2000 epochs looks about the same quality as the 1000 epoch one.

![Example after 2000 epochs](https://github.com/jonDuke/GAN_training/blob/main/CIFAR10/Images/cat_generated_plot_e2000.png?raw=true)

In the end, I'd say this is about the same level of quality we got from the original model using all of the pictures at once.  So how would I improve it?  At this point I don't yet know, but my guess would be that either a larger dataset or a different model design would be needed.  

Again, the final model weights are available [here](https://github.com/jonDuke/GAN_training/blob/main/CIFAR10/Models/cat_generator_model_2000.h5).

## What's next?

The dataset especially could use work, there's only so much information you can fit in a 32x32 pixel image.  With higher quality, there would be more information there for the model to learn.

And of course there are several GAN models in use out there today.  I'll have to research them and try a couple.

That about wraps up the time I'll spend with the CIFAR10 set.  Whatever's next will depend on what I find during my research.  Stay tuned!
