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
