# Enhancing Arabic Sign Language Recognition using Saudi Arabian Dataset: VideoMAE and Data Augmentation Techniques
This README file provides an overview of the research paper titled "Arabic Sign Language Recognition." It summarizes the objectives, Dataset, methodology, key findings, and potential applications of the study. Please note that this README serves as a concise summary, and for more detailed information, it is recommended to refer to the original paper.

## Paper Information

Title: Arabic Sign Language Recognition

Authors: [Author 1]

Keywords: Transformer, Deaf community, Attention model, Arabic sign language (ArSL) <br>

## Summary
The research paper "Arabic Sign Language Recognition" presents an approach for automatic recognition of Arabic sign language words from video data. The authors developed a new dataset specifically designed for Arabic sign language and evaluated state-of-the-art deep learning techniques to achieve accurate recognition. The paper highlights the potential of computer vision and language models in understanding and interpreting sign language communication.

## Dataset

The dataset contains video recordings of 587 unique Arabic sign words collected from the [Saudi Sign Language Association website](https://sshi.sa/). Each word is expressed in a separate video clip. 

![An illustrative video excerpt from the dataset](https://github.com/Ali-Almalki/paper1/blob/main/img/An%20illustrative%20video%20excerpt%20from%20the%20dataset.png)

The data can be found here:[Dataset](https://drive.google.com/drive/folders/1QE_SFWeMctKg4va-GOom5fXMNm94lgeX?usp=drive_link)

The words cover categories such as directions, attributes, shapes, education, environment, home, health, social relations, opposites, jobs etc.


The dataset was split  for training, validation and testing.

For each word :

- **Train** - Contains the original video clip (e.g. word_0.mp4) and two augmented copies generated using color inversion (word_0_transformedInvertColor.mp4) and multiply (word_0_transformed_Multiply.mp4) transforms. 

- **Val** - Contains a downsampled version of the original clip for validation.

- **Test** - Contains a separate downsampled version of the original clip for testing.
 
dataset structure diagram :

          |
          
          +-- Train 
          
          |    |
          
          |    +-- word_0.mp4
          
          |    +-- word_0_transformedInvertColor.mp4 
          
          |    +-- word_0_transformed_Multiply.mp4
          
          |
          +-- Val
          
          |    |
          
          |    +-- word_0_downsampled.mp4
          
          |
          
          +-- Test
          
               |  
               
               +-- word_0_downsampled.mp4
               
| The output of color inversion augmentation | The output of downsampling augmentation | The output of multiplication augmentation |
|---------|---------|---------|
| ![The output of color inversion augmentation](https://github.com/Ali-Almalki/paper1/blob/main/img/The%20output%20of%20color%20inversion%20augmentation.png) | ![The output of downsampling augmentation](https://github.com/Ali-Almalki/paper1/blob/main/img/The%20output%20of%20downsampling%20augmentation.png) | ![The output of multiplication augmentation](https://github.com/Ali-Almalki/paper1/blob/main/img/The%20output%20of%20multiplication%20augmentation.png) |

## Methodology
The authors employed a two-step methodology for Arabic sign language recognition. Firstly, they fine-tuned the VideoMAE model separately on 15 independent subsets, each representing a unique sign word category. The model was trained for 4 epochs using default hyperparameters. Secondly, to improve recognition ability, the authors applied robust data augmentation techniques during training, including color inversion, downsampling, and multiplication. They increased the number of epochs to 16 to allow the models to learn richer representations from the augmented data. 

## Architectures details of VideoMAE

The VideoMAE model serves as the backbone architecture for our Arabic sign language (ASL) word recognition system. VideoMAE consists of a masked autoencoder that encodes videos into a latent space representation and reconstructs the original videos from this representation. The model is pretrained on the Kinetics-400 dataset, which provides a rich source of diverse video data. By leveraging the pretraining, we enable the model to learn general features and temporal patterns that are relevant for video understanding tasks.
The VideoMAE architecture is complemented with a vanilla vision transformer (ViT) backbone. The ViT component enhances the model's ability to capture spatial features and provides a strong foundation for visual representation learning.
By combining the power of masked autoencoders with the spatial modeling capabilities of ViT, our proposed architecture achieves improved performance in ASL word recognition.

![VideoMAE Architecture](https://github.com/Ali-Almalki/paper1/blob/main/img/VideoMAE%20Architecture.jpg)

## Results
The project's evaluation demonstrates the effectiveness of the proposed approach. The average accuracy achieved across the 15 fine-tuned models was 97% on the test set. By employing data augmentation techniques and increasing the number of training epochs, the average test accuracy for individual models improved to 97%. The combined predictions from all models yielded an overall test accuracy of 97% on unseen data.

  ### - Model Performance across Datasets 

<p align="center">
  <img src="https://github.com/Ali-Almalki/paper1/blob/main/img/Model%20Performance%20on%20Datasets%200%20to%204.png" alt="Model Performance on Datasets 0 to 4" width="30%">
  <img src="https://github.com/Ali-Almalki/paper1/blob/main/img/Model%20Performance%20on%20Datasets%205%20to%209.png" alt="Model Performance on Datasets 5 to 9" width="30%">
  <img src="https://github.com/Ali-Almalki/paper1/blob/main/img/Model%20Performance%20on%20Datasets%2010%20to%2014.png" alt="Model Performance on Datasets 10 to 14" width="30%">
</p>

  ### - Model's Word Prediction for video 

![Model's Word Prediction for a Video1](https://github.com/Ali-Almalki/paper1/blob/main/img/Model's%20Word%20Prediction%20for%20a%20Video1.png)
![Model's Word Prediction for a Video2](https://github.com/Ali-Almalki/paper1/blob/main/img/Model's%20Word%20Prediction%20for%20a%20Video2.png)

  ### - Validation Loss and Accuracy on Dataset 14 
  
![Validation Loss and Accuracy on Dataset 14](https://github.com/Ali-Almalki/paper1/blob/main/img/Validation%20Loss%20and%20Accuracy%20on%20Dataset%2014.png)

## Applications
The findings of this research have several potential applications, including:

Arabic sign language interpretation software: The accurate recognition of Arabic sign language words can be integrated into interpretation software, enabling real-time translation of sign language conversations into spoken or written language.

Sign language education: Robust recognition systems at the word level can enhance the learning experience for sign language learners by providing instant feedback and guidance.

## Future Work

Expanding the dataset diversity by including more signers and additional word types such as letters, numbers and verb conjugations. Benchmarking additional deep learning models.

## Usage

The Jupyter notebooks in this repository demonstrate the data preprocessing, model training and evaluation steps. Feel free to adapt the code for your needs.




