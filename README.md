Authors: Emmy Veselinov, Jubayer Ahmed, Eric Li
# Stock Prediction with CNN-TA

Building and using a CNN to predict hold, buy, and sell points on historical time series stock data.

# Dataset
![image](https://github.com/emmyvese12/CNN-stock-prediction/assets/66185881/1cadfd0d-c506-492d-8884-7d25e983e754)
Financial images are produced using historical IBM data from 2004-2024 from Yahoo Finance. A subset of data from 2004-2019 is used to create images for training and testing. The second set of data from 2020-2024 is used for backtesting.

![image](https://github.com/emmyvese12/CNN-stock-prediction/assets/66185881/fe7f8ecd-549f-41e6-866d-ca1e5415ca0a)
A three-class subset of the CIFAR-10 dataset containing 5000 images per class is used for training the model, and 1000 images per class are used for testing.

# Approach
![image](https://github.com/emmyvese12/CNN-stock-prediction/assets/66185881/15d58a2d-9f30-4b06-99f1-9c481a5d64f6)
A set of 500 financial indicators are calculated from the IBM data set. The 225 best features are selected using a combination of univariate feature selection methods prior to creating images. The architecture of the CNN proposed by the research paper is remodeled by replacing max pooling layers with additional dropout layers for increased class prediction accuracy. 

# Generated Images
![image](https://github.com/emmyvese12/CNN-stock-prediction/assets/66185881/2cb4844e-887c-436d-9919-9afb974dbd66)

# Results
- Best 3 class confusion matrix for Hold, Buy, and Sell with sample class weights:

![image](https://github.com/emmyvese12/CNN-stock-prediction/assets/66185881/280476ac-c046-4cb2-a1e4-219f6cded86d)

- Backtester results on IBM data from 2020-2024 using trading strategy defined by trained CNN:

![image](https://github.com/emmyvese12/CNN-stock-prediction/assets/66185881/77bcdeb8-4276-466b-869b-de6b30eee952)

---
- Best 3 class confusion matrix for animal classification:

![image](https://github.com/emmyvese12/CNN-stock-prediction/assets/66185881/14ae6150-b328-460a-82da-5af5259b4503)
  
# Method Pipeline
**The following notebooks can be run in order from 1-9 to replicate the implemented pipeline.** The details of each section are listed below:

1. Process Stock Data - Fetches IBM finance data from Yahoo Finance.
2. Label Stock Data - Each trading day is labeled Hold, Buy, or Sell using a labelling algorithm.
3. Calculate Initial Indicators - Financial indicators calculated from IBM data using sliding windows to create initial 225 features.  
4. Original Stock CNN - CNN model proposed by Sezer et al. is defined, trained, and validated.
5. Expand Indicators - Additional indicators are calculated to increase number of features.
6. Feature Selection - Univariate feature selection to select top 225 best features.
7. Stock CNN 2k - Modified CNN model is defined, trained, validated, and tested on IBM data from 2004-2019.
8. Backtester - Backtesting using trained IBM model on a given stock to measure financial success of CNN on the market.
10. Animal CNN - Modified CNN architecture is trained and tested using CIFAR-10 dataset.

# Referenced Paper
[1] Sezer, Omer & Ozbayoglu, Murat. (2018). Algorithmic Financial Trading with Deep Convolutional Neural Networks: Time Series to Image Conversion Approach, https://www.researchgate.net/publication/324802031_Algorithmic_Financial_Trading_with_Deep_Convolutional_Neural_Networks_Time_Series_to_Image_Conversion_Approach.
