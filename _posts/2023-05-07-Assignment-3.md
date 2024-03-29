---
layout: post
title: Assignment 3 
excerpt: "Image Assignment"
modified: 5/07/2023, 7:27:24
tags: [intro, beginner, jekyll, tutorial]
comments: true
category: blog
---
[The google drive link to all the images used in this assignment](https://drive.google.com/drive/folders/1-EMU82xMCuYwnoKNSAnFlOFNJcVWoRPK?usp=share_link)

For the image classification assignment, Nikita and I selected two datasets using Instagram and Google Images. We chose four random fashion photographers from Instagram, namely Brandon Woelfel, Theo Wenner, Petra Collins and Faye, whose images mainly focus on the manipulation of light. 

<img src="/images/img1.jpeg" style="width:80%; height:50%; margin-left:10%;" />

We attempted to use the clustering method shown in video 14 but found that it did not work well for our dataset. Unlike the example shown in the tutorial, it was unable to cluster images from the same photographer together and instead mixed them with images from other photographers. We initially thought that Orange was classifying images based on lighting, but upon closer examination, we realized that it was having difficulty distinguishing between images that had similar compositions, even if they were taken by different photographers. 

<img src="/images/img2.png" style="width:80%; height:50%; margin-left:10%;" />

For example, images of Brandon were mixed with an image from Petra because they had a similar composition, despite the differences in lighting.

<img src="/images/img3.png" style="width:80%; height:50%; margin-left:10%;" />

Similarly, we saw this in another cluster where the images of Petra were mixed with one from Faye, despite the lighting being different in all four images. The commonality lay in the composition, where they both had their subjects' faces zoomed in for portraits. 

<img src="/images/img4.jpeg" style="width:80%; height:50%; margin-left:10%;" />

When we examined a cluster where all four photographers were together, we suspected that the algorithm was picking up on the features of the subjects,such as hair and eye color, in addition to the photographic style. In the image classification task, we had to choose a different dataset of 100 images as the previous dataset with 40 images and 4 photographers did not yield satisfactory results. For this, we selected 10 different colors of outfits in wedding couple photos, namely pink, white, blue, green, black, orange, red, yellow, light green, and purple, randomly obtained from Google. 

<img src="/images/img5.jpeg" style="width:80%; height:50%; margin-left:10%;" />

The confusion matrix obtained from the analysis revealed that white and dark green were the most accurately predicted colors, with a value of 6, followed by black, light green, and yellow, with a value of 5. Orange and pink had a value of 4, while purple had a value of 3, and blue and red had the lowest value of 2, as the algorithm often confused them with other similar colors, thus lacking accuracy. An interesting observation from the confusion matrix was that there were instances where the probability of a color being confused with a predicted color was high, but not vice versa. This indicated that if the algorithm perceived a color to be another similar color, it would not necessarily confuse the other color with the first one, as the second color could be more evident in the image, forcing the algorithm to identify it as that color. For example, in the confusion matrix, the actual color orange had a predicted value of 3 of being perceived as yellow, whereas in the reverse case, where the actual color was yellow, it had a predicted value of 2 of being predicted as orange. This was due to the visible presence of yellow in the image, which was easily identified by the algorithm. Similar cases were noticeable in blue and purple, black and dark green, and so on. 

<img src="/images/img6.png" style="width:80%; height:50%; margin-left:10%;" />

In this task, Orange performed well in classifying images, and instances where it did confuse two colors were understandable. For instance, it classified two images from the category of white as red because there was a pop of red color in those two images.

Salvaggio's argument bears significance in comprehending and grouping both datasets of images using Orange, particularly concerning the role of context in creating and selecting datasets. The algorithm is trained on the data and therefore constrained by the biases and assumptions inherent in the dataset. In the case of the fashion photographer dataset, Orange faced difficulties in accurately comprehending and grouping images of the collection. The homogenous shooting style among the photographers could be influenced by cultural, political, social, and economic factors, reflecting their common Western background. Our observation during the hierarchical clustering revealed that images from various photographers were clustered together if they shared similar features, which could again be traced back to contextual influences. Another aspect that surfaced during our analysis was that Orange offers various image embedding options, each using a distinct model architecture to extract photo features. The embedding setting can affect the outcomes, as each one is optimized to extract different types of characteristics from photos. For example, if the dataset contains faces, the OpenFaces embedding setting might produce superior results compared to other options. Similarly, if the dataset has general images such as landscapes or animal photographs, Inception v3 or VGG16 settings may perform better. We experimented with various embedding settings and chose Inception and VGG-16 settings that worked best with each dataset.

The concept of "distant viewing" introduced by Arnold and Tilton is concerned with the use of computational methods and machine learning algorithms to analyze large collections of visual materials, such as images or videos. Our study draws parallels with this concept in that we used Orange's hierarchical clustering algorithm to analyze our dataset of fashion photographs and wedding couple photos, thus enabling us to extract metadata in the form of clusters and confusion matrices that helped us interpret patterns and relationships in the data. Arnold and Tilton's view of "distant viewing" as a form of explicitly interpretive analysis is relevant to our study, as we had to interpret the clusters and confusion matrices produced by the algorithm to understand the patterns in the data. This required us to consider factors such as the framing and composition of the photographs, as well as the cultural and social contexts in which they were produced, in order to make sense of the clustering results.

During our exercise, we also discussed the categorization of our personal Instagram pages and found it to be an interesting topic. It made us reflect on how our pages categorize us based on the content we post, providing personal information about our interests, hobbies, and even our moods and feelings when capturing the images. For example, Nikitas' Instagram page primarily features beach photographs, indicating her love for the beach and potentially her interest in water sports. In contrast, my Instagram page has random pictures of myself with friends and dogs, portraying my personal life and relationships.

This exercise brought to our attention the ethical considerations that arise when gathering, using, and sharing data, especially when dealing with pictures. The use of photographs from Instagram or Google raises questions about the ownership and consent of the individuals in the images. These concerns become even more pressing when we consider that image analysis algorithms may perpetuate prejudices and stereotypes, leading to harmful effects on individuals or groups. Thus, it is essential to be mindful of such biases and take steps to address them, such as ensuring diversity in the training data and assessing the algorithm's outputs for fairness and accuracy.

We also learned that data selection and preparation can have a significant impact on the performance of machine learning algorithms. In our case, we made sure to choose images that were openly available for public use and selected them randomly without any bias. However, data selection may not always be straightforward or transparent, and researchers must be vigilant in assessing the potential biases and limitations of their datasets. This exercise has provided us with valuable insights into the ethical considerations and challenges that arise when using machine learning algorithms to analyze visual materials. It has also emphasized the importance of being mindful of biases and limitations in the data and algorithms used and being explicitly interpretive in analyzing the results.
