Please read the instructions carefully.
Program-1 
Use the alexnet program and modify it to the conditions given below. Use the database
MNIST already present in the pytorch. Instead of FashionMNIST it will be MNIST. Number of
Classes in this dataset is 10. MNIST is a dataset to identify numbers, so the number of
classes is 10. Make the batch size 16 and epoch should be 1 or 2.


Layer1:
1. Input will be 1 channel i.e grayscale images
2. Apply 96 kernels, of kernel size 11, stride of 4 and padding of 0
3. Apply activation function ReLU
Layer2:


1. Apply 96 kernels, kernel size 1
2. Apply activation function ReLU
Layer3:
1. Apply 96 kernel, kernel size 1
2. Apply activation function ReLU
3. Do a maxpool2d, kernel size of 3 and stride2
4. Dropout of 0.5
Layer4:
1. Apply 256 kernel (hint the input to this conv2d layer is still 96) of size 11, stride 4 and
padding 2
2. Apply activation function ReLU
Layer5:
1. Apply 256 kernels, kernel size of 1
2. Apply activation function ReLU
Layer6:
1. Apply 256 kernels, kernel size of 1
2. Apply activation function ReLU
3. Maxpool2d, kernel size of 3 and stride of 2.
4. Dropout of 0.5
Layer7:
1. Apply 384 kernels of size 3, stride of 1 and padding of 1
2. Apply activation function ReLU
Layer8:
1. Apply 384 kernels of size 1
2. Apply activation function ReLU
Layer 9:
1. Apply 384 kernels of size 1
2. Apply activation function ReLU
3. Dropout of 0.5
Layer 10
1. Apply 10 kernel (hint the input to this layer is 384) of kernel size 3, stride of 1 and
padding of 1
2. Apply activation function ReLU
Layer 11:
1. Apply 10 kernels of kernel size 1
2. Apply activation function ReLU
Layer 12:
1. Apply 10 kernels of kernel size 1
2. Apply activation function ReLU
3. Finally apply nn.AdaptiveAvgPool2d((1, 1)) to the final output.
There is no fully connected layer in this network; it is in the alexnet code that I have given.
Modify the alexnet code appropriately.

<=========================================================================================================================================================================================================>


Program-2:
Use the database MNIST already present in the pytorch. Instead of FashionMNIST it will be
MNIST. Number of Classes in this dataset is 10. MNIST is a dataset to identify numbers, so
the number of classes is 10. Make the batch size 16 and epoch should be 1 or 2.
Use the program you created for program-1 and layers-1 to layer-8 will be the same. Delete
the layers-9 to 11. Instead plug in a fully connected (fc) layer (i.e. nn.Linear()).
Remember now you are using the fc layer so please go back and understand the fc layer of
alexnet. You have to flatten the data. Look carefully at the transform function, it is
transforming the images into 224x224 images. MNIST data are usually 28x28. The
transformation is scaling the data. So the input data will be 224x224 and grayscale (i.e. one
input channel)
The conditions are:
A. In case of alexnet the input was 5*5*256, in this case the input will be X * Y * 384.
Look at the output channel size of the last layer (i.e. previous to this layer). Calculate
X and Y yourself. Remember the input image is of size 224x224 in the layer-1
because of transformation. Take help from the alexnet code and slide-8 of
“introduction to Neural Network-II”. Important: In pytorch for output size determination
they use the floor function.
Layer-9:
1. Input channel to fc (or nn.Linear) will be X * Y * 384 and output will be 4096
2. Apply activation function ReLU
3. Dropout of 0.5
Layer-10:
1. Input channel to fc (or nn.Linear) will be 4096 and output will be 4096
2. Apply activation function ReLU
3. Dropout of 0.5
Layer-11:(actually this is not a layer but anyways)
1. Input channel to fc (or nn.Linear) will be 4096 and output will be Classes (number of
classes)

<==========================================================================================================================================================================================================>





BONUS QUESTION:
If you are able to draw the diagram of the network given in either program-1 or program-2 in
the manner shown in slide number 8 of “introduction to Neural Network-II” slide deck. Upload
the image into github.
