# SageMaker Deployment Project

Please see the [README](https://github.com/udacity/sagemaker-deployment/tree/master/README.md) in the root directory for instructions on setting up a SageMaker notebook and downloading the project files (as well as the other notebooks).

# General Outline
1. Download or otherwise retrieve the data.
  - [aclImdb_v1](http://ai.stanford.edu/~amaas/data/sentiment/aclImdb_v1.tar.gz)
2. Process / Prepare the data.
  - Using BeautifulSoup to remove html tags and tokenize the reviews.
  - Build a bag of words model for mapping 5000 most frequent appearning words to a unique integer.
  - Transform the review to uni-length (500) with zero-padding.
3. Upload the processed data to S3.
4. Train a chosen model.
  - RNN -> LSTM units with 32 embedding dim and 200 hidden_dim. 
  - 10 epcohs of training, Binary Cross Entropy Loss from 0.6656 dropped to 0.3045.
5. Test the trained model (typically using a batch transform job).
  - Accuracy ** 83.4% ** with only 10 epoches.
6. Deploy the trained model.
7. Use the deployed model.
