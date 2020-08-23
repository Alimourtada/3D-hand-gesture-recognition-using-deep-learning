<p align="center">
  <a href="" rel="noopener">
 <img width=200px height=200px src="data&utils/imagesMD/kaggle.png" alt="Project logo"></a>
</p>

<h3 align="center">3D hand gesture recognition using Deep Learning - Data Challenge Univ.Lille</h3>



---
Centrale Lille | [Anas ESSOUNAINI](https://www.linkedin.com/in/anas-essounaini-b7514014a/) |  [Ali MOURTADA](https://www.linkedin.com/in/ali-mourtada-57714214a/) | [Imad AOUALI](https://www.linkedin.com/in/imad-aouali/) | [Abdellah RAHMANI](https://www.linkedin.com/in/abdellah-rahmani-8010a3161/)

## 📝 Table of Contents

- [About](#about)
- [Repo structure](#repo)
- [Data description](#data)
- [Results](#rank)
- [Acknowledgments](#acknowledgement)

## 🧐 About <a name = "about"></a>

Recent virtual or augmented reality devices offer new 3D environment in which we need new and precise manner to interact. Hands can offer an intuitive and effective tool in these applications. Some gestures, as swipes, are more defined by the hand motion (called here coarse gesture) while others are defined by the hand shape through the gesture (called fine gesture). This difference between useful gestures have to be taken into account in a hand gesture recognition algorithm.

Effective and inexpensive depth sensors, like the Intel RealSense or the Leap Motion Controller provide precise skeletal data of the hand and fingers in the form of a full 3D skeleton corresponding to 22 joints. Hand skeletal data could handle a precise information of the hand shape that HCI applications need in order to use the hand as a manipulation tool. In this challenge, we present a 3D dynamic hand gesture dataset which provides sequences of hand gestures in the form of 3D skeletal data.

The Intel RealSense short range depth camera is used to collect our dataset.

<img src="data&utils/imagesMD/capture.png"
     alt="Markdown Monster icon"
     style="float: left; margin-right: 10px;" />


##   📒  Repo structure <a name='repo' ></a>

- documents : slides explaining our approach
- Notebook : google colab notebook with final approach
- data&utils : data used for training DNN and utils py functions

##  🔧 Data description <a name = "data"></a>

The dataset contains sequences of 14 hand gestures performed in two ways: using one finger and the whole hand. Each gesture is performed between 1 and 10 times by 28 participants in 2 ways, resulting in 2800 sequences. All participants are right handed. Sequences are labelled following their gesture, the number of fingers used, the performer and the trial. However, for this challenge, only the case of 28 class categories are considered (the same gesture performed using one finger and the whole hand gives rise to two different classes). Each frame of sequences contains the coordinates of 22 joints both in the 2D depth image space and in the 3D world space forming a full hand skeleton. The Intel RealSense short range depth camera is used to collect our dataset. The skeletons were captured at 30 frames per second.

Data and utils : [link](./data&utils/) (data is zipped)

### File descriptions

- skeletons_image_train.csv and skeletons_world_train.csv - the training subset. They have respectively a shape as (1960, 171, 22, 2) and (1960, 171, 22, 3), containing 1960 gesture sequences (70% of the dataset) of maximum size of 171 frames (padding is considered). Each frame is represented by 22 hand joints coordinates expressed respectively in the depth image and 3D world spaces.
  
- skeletons_image_test.csv and skeletons_world_test.csv - the test subset They have respectively a shape as (840, 162, 22, 2) and (840, 162, 22, 3), containing 840 gesture sequences (30% of the dataset) of maximum size of 162 frames (padding is considered). Each frame is represented by 22 hand joints coordinates expressed respectively in the depth image and 3D world spaces.

- info_train.csv - information about training subset expressed as a matrix of size 1960 lines, each one expressed as (idx, label, sequence length with non zero padding frames).

- info_test.csv - information about test subset expressed as as a matrix of size 840 lines, each one expressed as (idx, label, sequence length with non zero padding frames).

- load_and_display_data.py a python script which allow to read data files and display a sequence of 2d skeleton. Dependencies for the python script: numpy, csv and matplotlib. Not that, the order of the joints in the line is: 1.Wrist, 2.Palm, 3.thumb_base, 4.thumb_first_joint, 5.thumb_second_joint, 6.thumb_tip, 7.index_base, 8.index_first_joint, 9.index_second_joint, 10.index_tip, 11.middle_base, 12.middle_first_joint, 13.middle_second_joint, 14.middle_tip, 15.ring_base, 16.ring_first_joint, 17.ring_second_joint, 18.ring_tip, 19.pinky_base, 20.pinky_first_joint, 21.pinky_second_joint, 22.pinky_tip.

- sampleSubmission.csv - a sample submission file in the correct format.

##  🎯 Results <a name = "rank"></a>

We ranked 1st with 92% accuracy ahead of second place with ~10 % in scoring.

## 🎉 Acknowledgements <a name = "acknowledgement"></a>

- Hat tip to Prof. **Wannous** for this wonderful and enriching challenge ! 
- Many thanks for my teamates Ali, Imad and Abdellah for the fun learning experience and determination to create a good classification model and have a good score in the kaggle competetion.
- References


  Quentin De Smedt, Hazem Wannous, Jean-Philippe Vandeborre: Heterogeneous hand gesture recognition using 3D dynamic skeletal data. Computer Vision and Image Understanding 181: 60-72 (2019)

  Quentin De Smedt, Hazem Wannous, Jean-Philippe Vandeborre, Joris Guerry, Bertrand Le Saux, David Filliat: 3D Hand Gesture Recognition Using a Depth and Skeletal Dataset. 3DOR 2017

  Dennis Ludl, Thomas Gulde, and Crist'obal Curio, Simple yet efficient real-time pose-based action recognition. In IEEE Intelligent Computer Science ITSC 2019

  Chao Li ; Qiaoyong Zhong ; Di Xie, Shiliang Pu, Skeleton-based action recognition with convolutional neural networks, IEEE International Conference on Multimedia & Expo Workshops (ICMEW 2017)

  Chuankun Li ; Yonghong Hou ; Pichao Wang ; Wanqing Li, Joint Distance Maps Based Action Recognition with Convolutional Neural Networks, IEEE Signal Processing Letters, Vol: 24 , Issue: 5, May 2017

  Chuankun Li ; Pichao Wang ; Shuang Wang ; Yonghong Hou ; Wanqing Li, Skeleton-based action recognition using LSTM and CNN, IEEE International Conference on Multimedia & Expo Workshops (ICMEW 2017)
  
