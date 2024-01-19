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

## Methodology
The authors employed a two-step methodology for Arabic sign language recognition. Firstly, they fine-tuned the VideoMAE model separately on 15 independent subsets, each representing a unique sign word category. The model was trained for 4 epochs using default hyperparameters. Secondly, to improve recognition ability, the authors applied robust data augmentation techniques during training, including color inversion, downsampling, and multiplication. They increased the number of epochs to 16 to allow the models to learn richer representations from the augmented data.    

## Applications
The findings of this research have several potential applications, including:

Arabic sign language interpretation software: The accurate recognition of Arabic sign language words can be integrated into interpretation software, enabling real-time translation of sign language conversations into spoken or written language.

Sign language education: Robust recognition systems at the word level can enhance the learning experience for sign language learners by providing instant feedback and guidance.

## Future Work

Expanding the dataset diversity by including more signers and additional word types such as letters, numbers and verb conjugations. Benchmarking additional deep learning models.

## Usage

The Jupyter notebooks in this repository demonstrate the data preprocessing, model training and evaluation steps. Feel free to adapt the code for your needs.




