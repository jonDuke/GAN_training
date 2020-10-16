# MNIST GAN

This is the second project added to this repository, and has a lot of similarities with the first one.  Here I follow an official tensorflow tutorial [found here](https://www.tensorflow.org/tutorials/generative/dcgan).  While the CIFAR10 tutorial was very descriptive and useful, this one makes much better use of the TensorFlow API, which is a very good thing to learn.

This time I trained a Deep Convolutional GAN on the MNIST dataset, a collection of images of handwritten numbers. The model itself is structured very similarly to the one used in the CIFAR10 project, which was also trained on a set of small image files.

The big difference here, is that the images are only black and white, and handwritten numbers are much simpler than images of cats and dogs.  This time, it was very easy to train a GAN that could produce convincing fake images of handwritten numbers.

## Tutorial Results

Another cool thing about this tutorial, it included code that compiled all the example images generated during training into a GIF.  These example images were all generated from the same random seed, so this is a cool timelapse of how the GAN developed better images over time.

![MNIST training gif](https://github.com/jonDuke/GAN_training/blob/main/MNIST/Images/dcgan.gif?raw=true)

This network only took 50 epochs to get these results, much faster than my attempts with the CIFAR10 dataset.  It is interesting to see that some of them shifted between numbers as the training progressed.

While that random seed ended up giving a lot of "9" images in the end, other seeds of course give us other results.  The images are not all perfect, but many of them could easily be real images of handwritten numbers.

![Trained example](https://github.com/jonDuke/GAN_training/blob/main/MNIST/Images/example_output.png?raw=true)

## Next Steps

The tutorial itself suggests trying this GAN code on other datasets, and that's exactly what I'm going to do next.  Stay tuned!
