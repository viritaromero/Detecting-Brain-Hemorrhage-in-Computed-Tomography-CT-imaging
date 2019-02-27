

![alt text](https://cdn-images-1.medium.com/max/716/1*j09PgBpdJIHXhlyjcby0HA.jpeg)


# When biology meets Big Data

Deep Learning applied in healthcare can contribute to saving time between medical imaging, diagnosis and beginning treatment. Automated diagnosis can be done within seconds, thanks to these computer vision models.

Although deep learning can help to detect anomalies in medical imaging, finding valuable datasets and pre-processing this data could be painful.

In this post, I will diagnose brain hemorrhage by using deep learning, Computed Tomographies (CT) of the brain and my favorite deep learning framework: PyTorch.

# What’s a Computed Tomography of the brain?

A CT of the brain is a noninvasive diagnostic imaging procedure that uses special X-rays measurements to produce horizontal, or axial, images (often called slices) of the brain. Brain CT scans can provide more detailed information about brain tissue and brain structures than standard X-rays of the head, thus providing more data related to injuries and/or diseases of the brain.

# No ImageNet equivalent to medical imaging

Convolutional Neural Networks are pre-trained with non-medical images such Densenet, Inception and Alexnet, but once we pick the last fully-connected layer to train (transfer learning), it’s an excellent technique for achieving our specific goal.
The Dataset

# Head CT-Hemorrhage (Balanced Normal vs Hemorrhage Head CTs)

The dataset contains 100 normal head CT slices and 100 with hemorrhage. I won’t classify the different kinds of hemorrhage, My goal is to predict if the CT slices present hemorrhage or it’s a normal head.

You can find the dataset here:

https://www.kaggle.com/felipekitamura/head-ct-hemorrhage



# Data Augmentations

To achieve a good accuracy I tried to use different data augmentations.

What’s data augmentation?

We know that the more data we have, our model will perform better. But collecting a good amount of data from the wild could be a hard task.

Data augmentation is a technique used in deep learning that augments the size of the current data instead of collecting data from the wild.

Some data augmentations examples are: adding noise or applying data transformations such horizontal and vertical flips and color distortions.


By augmenting your dataset, you can achieve excellent results with a small amount of data. I did a little research about data augmentations used specifically for medical imaging and it happens that when you add contrast to the images, model achieves a better accuracy. A variety of augmentation strategies can be used to get better results.
Training the model

I chose again the pre-trained model Resnet-152. As done in past projects, I only trained the last fully-connected layer of Resnet-152.

80% of the dataset was used for training and 20% for testing.

The experiment shows that Resnet-152 achieves an accuracy of 95% in 10 epochs run on the dataset!

# Conclusions

Deep Learning techniques can help physicians detecting brain hemorrhage in CTs brain, but the classification result much depends on the amount of data used during the training process. So, as said before, try different data augmentations to get a higher accuracy or you may need to use a good web scraper to collect your data (that’s a good thing, I’ve been using ScrapeStorm to collect data for other projects).

Think about how can you apply deep learning that requires the use of medical imaging…what about detecting depression in brain scans? or detecting alcoholism? Many diseases like these alter brain structure and you can use a computer vision model and medical imaging to get interesting results.

# Read more about this project:
https://medium.com/datadriveninvestor/detecting-brain-hemorrhage-in-computed-tomography-ct-imaging-d1276cb6bdb7
