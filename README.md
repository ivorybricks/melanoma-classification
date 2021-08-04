# melanoma-classification

## About the Project:
This repository contains some files that show my process of working on the SIIM-ISIC Melanoma Classification project. 

Project Goal: Given images of skin lesions, determine the probability that each lesion represents melanoma. 

View SIIM-ISIC Melanoma Classification prediction competition: 
https://www.kaggle.com/c/siim-isic-melanoma-classification/ 

## More Specifics on Repository Files
During this project, I worked with both structured (.csv) and unstructured data (.jpeg images).

_Most Relevant Files:_
- **XGBoost-v4.ipynb** - My final version using the XGBoost model on the structured data.
- **melanoma_cnn_v2.ipynb** - My final version using the CNN model on images cropped based on salient regions.
- **Statistical Notes on train.csv.ipynb** - File in which I run a bit of exploratory analysis on the structured data.
- **xgboost_cnn_combined.ipynb** - File in which I average the target results from models seen in XGBoost-v4.ipynb and melanoma_cnn_v2.ipynb with weights based on each model's performance. 
- **melanoma_salient_region_detection.ipynb** - File showing the process of cropping unstructured data (.jpeg images) based on salient region. 

_Other Files:_
- **hair_augmentation.ipynb** - Adding hair augmentation to .jpeg images. (Did not use with final CNN model since hair augmentation did not sufficiently improve results.)
- **melanoma_gaussian_blur.ipynb** - Adding Gaussian blur to .jpeg images. (Did not use with final CNN model since blur did not sufficiently improve results.)
- **melanoma_transfer_learning.ipynb** - Transfer learning on structured data. (Did not sufficiently improve results.)
- **XGBoost - XGBoost-v3.ipynb** - Previous attempts utilizing XGBoost model.
- **melanoma_cnn_v1.ipynb** - First attempt utilizing CNN model.

## Summary of Results
_Some results excluded for brevity._

Based on Kaggle's Private Score (received by scoring predictions against the private portion of data, hidden until all submissions are received), my highest scoring predictions were those resembling or generated from **xgboost_cnn_combined.ipynb**. (These were the predictions created by taking a weighted average of **XGBoost-v4.ipynb** and **melanoma_cnn_v2.ipynb** predictions.) The highest of these scores was 0.7919. 

Predictions based on salient cropped images (such as predictions from **melanoma_cnn_v2.ipynb** alone) performed alright, receiving scores from 0.7060 to 0.7591. Transfer learning predictions scored 0.5027 to 0.6506, Gaussian blurred predictions scored 0.5090 to 0.7041, and hair augmented images scored 0.6039 to 0.6689. Predictions from previous versions using XGBoost scored the worst at around 0.5 and 0.64. 
