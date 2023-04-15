# Modified Residual Network for CIFAR-10 Image Classification
>  ECE-GY 7123: Deep Learning (Spring 2023) Mini-Project
>  
>  Team Members: Spriha Jha, Kabir Jaiswal, Nigam Patel

### 1. Abstract
In order to adhere to a restriction of less than 5 million parameters, we created and implemented a modified Residual Network (ResNet) architecture in this research. The goal was to achieve the maximum test accuracy on the CIFAR-10 image classification dataset. To create our final model, we investigated a range of architectural options and arrangements. Our updated ResNet architecture used 2,797,610 parameters and obtained a test accuracy of 94.17%.

### 2. Introduction
In the field of computer vision, the CIFAR-10 dataset is a frequently used benchmark for image classification tasks. It has 60,000 32x32 color photos that are split up into 10 classes, each with 6,000 images. 50,000 photos make up the training set, while 10,000 images make up the test set. The ten classes—which represent a wide variety of items frequently seen in daily life—include an automobile, a bird, a cat, a deer, a dog, a frog, a horse, a ship, and a truck. Due to the considerable intra-class variability and relatively low image resolution in this dataset, it is an excellent candidate for testing the effectiveness and durability of different deep learning models in image classification tasks. 

![Cifar-10](https://user-images.githubusercontent.com/20396145/232173766-07925e81-098d-40cb-81f1-86a60fafecf5.png)

Source: https://www.cs.toronto.edu/~kriz/cifar.html

### 3. Methodology

#### 3.1 Data Preparation
The CIFAR-10 dataset was downloaded and loaded using the torchvision program. To increase the generalization of the model, data augmentation techniques including random horizontal flips and random cropping were used. Using mean and standard deviation values of 0.5, the dataset was standardized.

#### 3.2 Model Design
Four residual layers, each with a different number of building blocks, follow the initial convolutional layer in our modified ResNet model. To decrease the spatial dimensions while increasing the number of channels, we used downsampling in the residual layers with a stride of 2. The output was passed to a fully connected layer for classification after adaptive average pooling.

The amount of fundamental blocks, channels, and stride values were a few of the architectural options we experimented with. Based on its ability to strike a compromise between precision and the restriction on the number of parameters, the final architecture was selected.

#### 3.3 Model Training
Stochastic Gradient Descent (SGD) was used to train the model, using a learning rate of 0.1, momentum of 0.9, and weight decay of 5e-4. The maximum number of epochs for the Cosine Annealing learning rate scheduler was 200. The loss function chosen was called cross-entropy loss.

### 4. Results
With 2,797,610 total parameters, our updated ResNet model's test accuracy was 94.17%. The model was trained over 200 epochs, with epoch 200 showing the highest test accuracy. The training accuracy was 99.964% at the last epoch.

### 5. Conclusion
In order to categorize CIFAR-10 images while following to the restriction of less than 5 million parameters, we successfully constructed a modified ResNet architecture in this project. The final model's test accuracy of 94.17% showed how well it performed picture classification tasks. The performance of the model may be significantly enhanced in the future work by investigating more architectural options, regularization methods, and training methodologies.


