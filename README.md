# :gear: Generative Adversarial Networks - GAN's

One of the hottest things to do with machine learning these days is to create some program that magically makes something that didn't exist before.  And one of the best ways to do that is with GAN's.  

This type of machine learning is something I've always had a curiosity about, so now I'm taking a deep dive and teaching myself all about them.  This repository will contain the code, notebooks, and examples I come up with along that journey.

## :question: What is a GAN, anyway?

GAN's are a special type of machine learning that combines multiple other models in order to generate something new.  This usually consists of two neural networks, one that generates a random image and one that classifies it as real or fake.  The two models are trained against each other, so as the classifier (or discriminator) gets better at spotting the fakes, the generator gets better at producing realistic outputs that fool the classifier.

One of the most more popular ways this has been implemented is with images.  After training a GAN on a set of images, say cats or people, the generator can produce images that look real and yet never actually existed.  You can see this very easily at sites such as [thispersondoesnotexist.com](https://thispersondoesnotexist.com/) or [thiscatdoesnotexist.com](https://thiscatdoesnotexist.com/), both of which use a GAN to generate a completely fake yet (usually) convincing image every time you reload the page.

GAN's can also be used with other things, of course, such as music or text.  Images are a well-explored space so I will be starting my studies on those.

# :computer: My Projects

What follows will be a quick overview of each individual project I've done.  Each project will have its own folder in this repository, where you can find more detail, source code, and sample outputs.

## [CIFAR10 GAN](https://github.com/jonDuke/GAN_training/tree/main/CIFAR10)

Starting off simple!  The CIFAR10 dataset was actually meant to be a beginner image classification set.  It consists of thousands of small images of various animals or objects.  The images themselves are only 32x32 pixels each, which means they will be quick to process and also makes this model relatively quick to train.  (these models took about 2 hours to train, but that's still relatively quick)

As for the results, well at least it was interesting.  In the end, I'd say a 32x32 pixel color picture just doesn't contain enough information for a neural network to learn to make convincing replicas.  You can clearly see the shapes it was trying to make in the final output, but a human can easily tell they aren't real pictures of cars, horses, or anything.  Here's an example of that final output:

![Example output](https://github.com/jonDuke/GAN_training/blob/main/CIFAR10/Images/generated_plot_e200.png?raw=true)

## Next up

:construction: More to come soon! :construction:
