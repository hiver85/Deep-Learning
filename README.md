# A short summary of using CNN to predict Mnist_fashion image dataset

## Introduction:
> Mnist_fashion is a built-in image dataset in Keras. It contains 70000 images of 28*28 pixels and categorized in 10 class from 0-9.
> In this personal project, I use CNN to predict the image's label. During the processing, some statistic such as train accuracy and test lost and visualisation will be done to see the effectiveness of the model and then turn on the parameters for better result.

## Process:
- Start with ploting some data
- Convert images to matrix 28 x 28 x 1for CNN
- Convert image to the range[-1,1]  
- Do one-hot encoding the label
- Train-test-split for testing and validation set 
- Build the model: 
  - Params: - batch_size = 64, epochs = 20, num_classes = num_label = 10
	    - padding='same', activation = linear & LeakyReLU
  - Layer: Conv2D -> 3 MaxPooling2D ->  softmax
  
- Check the effectiveness and modify the param: After the first model, the result get seems overfitted
  >- Test loss: 0.4897425325092394
  >- Test accuracy: 0.9165

- In this case, try to add the Dropout regulazation to avoid overfitting and check the effectiveness again 
  >- Test loss: 0.22862390214800835
  >- Test accuracy: 0.9196
This time, the result is better.

-Finally, verify true positive, false positive and ploting some result 
