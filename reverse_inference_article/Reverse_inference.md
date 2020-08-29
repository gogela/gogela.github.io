#'Reverse Inference' in deep neural networks
Trying to google the term Reverse Inference usually points you to neuropsychology articles. The articles usually refer to methods that try to identify one’s mental state from the observed brain activity. The methods mostly involve MRI of human brain that is used for more or less successful interpretation of patient’s ongoing cognitive process
[https://www.sciencedirect.com/science/article/pii/S1053811913000141]( https://www.sciencedirect.com/science/article/pii/S1053811913000141)

I have borrowed the fancy term for much simpler, while similar, problem.
Neuroscientists ask: I know very little about my patient’s brain, but how do I know what he/she feels or sees when the brain’s MRI looks like this?
My simple question is: I’m given a trained DNN, what the net sees on its input while I get this particular output?
There might be more approaches to such DNN ‘reverse engineering’. A very convenient method I used is based on GAN (Generative Adversarial Network). While GAN’s primary purpose is to train simultaneously both detector and generator, in our case the detector has been fully trained already and the training set in unknown.
For the following example we train a CNN on standard MNIST handwritten digits dataset. For an example of regular GAN on the same dataset, see: https://machinelearningmastery.com/how-to-develop-a-generative-adversarial-network-for-an-mnist-handwritten-digits-from-scratch-in-keras/
Google colab offers a very convenient environment for our experiment — so the following code extracts are optimized for it. Let’s start with training a CNN on the MNIST dataset to crate discriminator model:

First we prepare the environment and the training data:
