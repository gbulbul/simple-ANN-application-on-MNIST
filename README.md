
![MNIST_images](https://github.com/gbulbul/Recognizing-handwritten-numbers-by-a-simple-neural-net-and-CNN/assets/79763247/89d40c40-8d3f-439a-b9e0-11ff0ba91c25)


MNIST dataset is a benchmark dataset which was originally used to recognize handwritten numbers. MNIST has 10 classes, including (28*28) grey scale images of handwritten integers from 0 to 9. So, the task can be seen as a computer vision application when the aim is to detect images correctly as what the integer is on the given image. 


In this project, we constructed two models, namely, NN and CNN on MNIST, each was trained with 60000 images and tested on 10000 images.

![simple_NN_on_MNIST](https://github.com/gbulbul/simple-ANN-application-on-MNIST/assets/79763247/614d0fbc-05ae-46b7-8450-d0cffc0fc7e6)

The NN model is depicted above, as we see it is simple as it could be with one dense layer.


![mnist_simple_nn](https://github.com/gbulbul/simple-ANN-application-on-MNIST/assets/79763247/e8190dda-fa0b-40f4-9acd-8082bff9998b)

From the figure showing the confusion matrix, we can make a conclusion that how the model did on classification task where there are 10 categories of numbers when the images of handwritten numbers were used to train the model. 

![simple_nn_loss](https://github.com/gbulbul/Recognizing-handwritten-numbers-by-a-simple-neural-net-and-CNN/assets/79763247/62510d7e-f1b5-44ed-a635-aa545929271e)

The loss and accuracy plots suggest that the model on MNIST dataset is suitable in a way that good accuracy score is achieved by the model. From the plot, we may suspect that there could be more epoches to be trained on because accuracy-loss plots don't look stable as we expected to see.


Since CNNs are known for being successful at image detection, classification, a CNN model which is shown below was applied on MNIST to achieve the task of classifying the images of handwritten numbers.

![_CNN_on_MNIST](https://github.com/gbulbul/Recognizing-handwritten-numbers-by-a-simple-neural-net-and-CNN/assets/79763247/bc01be09-cecd-455b-821c-079d7d8a63e7)

CNN model that we applied on MNIST is shown above. If we talk elaborately on this model, it starts with 2D convolutional layer which uses 2D (3*3) arrays 32 times. Then, pooling methods was applied to pick the maximum of any 2D (2*2) array. This is followed by the flat layer. Later, a dense layer comes with its 100 nodes and all of its nodes were connected to the final(outcome) layer which has 10 nodes, each is for a prespecified class (from 0 to 9).

Technical details on modelling/fitting/compiling process:
-He uniform was used to initialize kernels at 2D convolutional and dense layers, independently.

-SGD was used as an optimization method with learning rate=0.01 and momentum=0.9.

-Same early stopping mechanism was used for both models to stop the fitting process in case there is no substantial increase in accuracy.

-Shape of Input for NN model: (28*28,)   &   Shape of Input for CNN model: (28,28,1) where (height,width,num_channel)=(28,28,1)


Loss-accuracy plots are presented here to observe how the CNN model performed on MNIST. Everything looks alright in the sense of as epoch increases, the loss decreases while the accuracy increases. Validation loss is a little greater than that of training as we expected. In terms of accuracy, starting at epoch 6, validation accuracy gets closer to the training accuracy. Then, they seem equal in the final.


![cnn_on_mnist_updated](https://github.com/gbulbul/Recognizing-handwritten-numbers-by-a-simple-neural-net-and-CNN/assets/79763247/c584ad60-131f-4970-9133-340ac858bcd6)

Loss-accuracy plots are presented here to observe how the CNN model performed on MNIST. Everything looks alright in the sense of as epoch increases, the loss decreases while the accuracy increases. Validation loss is a little greater than that of training as we expected. In terms of accuracy, at epoch 10, validation accuracy gets closer to the training accuracy.

![cnn_on_mnist_cm](https://github.com/gbulbul/Recognizing-handwritten-numbers-by-a-simple-neural-net-and-CNN/assets/79763247/865452c4-ac69-4a62-adfd-104191cc2b88)


CM on CNN model is provided below. As the entries on off-diagonal increases, the greater the misclassification error we get. On the contrary, in our case, CNN on MNIST did a good job of detecting classes correctly most of the time as we see from the CM plot.

Final notes: CNN did a good job on working with images as we expected, but also (simple, not deep) NN did a good job as well in terms of misclassification error. Both ended up with good accuracy scores and confusion matrices are the ones with a little misclassification error. The only thing we can suggest for NN application, it may need extra epoches to be trained on because its accuracy-loss plots weren't stabilized as we expected. 

So, both can be used to detect classes of images on MNIST.
