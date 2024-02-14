# Self-Supervised-Pretraining-With-Rotation-Classification-on-CIIFAR-10-Dataset

One important self-training task is the task of rotation classification. Here given a set of unlabeled images, we randomly rotate it to either of the following angles {0, 90, 180, 270} degrees and train a image rotation classifier which predicts by what angle the initial image has been rotated to generate the current image. The problem is set up as a classification problem since we only rotate our images by a fixed set of angles as mentioned before and the corresponding ground truth labels being {0, 1, 2, 3}.



<img width="750" alt="image" src="https://github.com/Aksheit-Saxena/Self-Supervised-Pretraining-With-Rotation-Classification-on-CIIFAR-10-Dataset/assets/58588004/9f7da086-6f5d-4b85-8aac-490594894911">



Once the self-training based pretraining is done, we strip away the final classification layer(which is a linear layer) and add Convolutional or linear layers as per the downstream task's requirement.


### Details of this problem statement.

1. Take the CIFAR-10 dataset, each class has 5000 samples and there are 10 classes.
Split the dataset in 2 parts (A) 40000 and (B) 10000 each with equal number of samples per class in each split.
2. Discard the labels of the samples in the first set.
3. Take a resnet-18 (initialised) and strip the imagenet classification layer with a 4 way classification layer.
4. Train this network on the self-training task of classifiying the rotation of the image.
5. Once this self-supervised pretraining is done, strip the classification layer and add a classification layer for CIFAR-10 classification this is finetuned on the set B for the task of image classification.
6. Log the loss(cross entropy) and accuracies for both the pre-training task and classfication task.

You are free tou use ML API of your choice. Your work will be checked for plagiarism!!

### Citations and helpful references 
[1]. https://www.youtube.com/watch?v=8L10w1KoOU8&t=694s <br>
[2]. https://openaccess.thecvf.com/content_CVPR_2019/papers/Feng_Self-Supervised_Representation_Learning_by_Rotation_Feature_Decoupling_CVPR_2019_paper.pdf
