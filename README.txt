The repository contains 4 Jupyter Notebook files as well as the raw dataset and a pre-trained Tweet2Vec model file. To test the code provided, run every cell in each notebook, this will create the files required to run the end-to-end system including the preprocessed data and the Tweet Embeddings.

Ensure that all relevant dependencies are installed before running each Jupyter notebook.

Run notebooks in the following order:

1. MP_Twitter_Scraper.ipynb

* This file contains the code used to compile the dataset used in this project, including the API keys required for the Twitter API.
* Run every cell in the notebook to download the Tweets from all MP Twitter Feeds for the relevent party. In order to select the required party, modify the "party" variable to contain either "Conservative", "Labour" or SNP.
* The Tweets will then be extracted. The final cell will save the CSV file into the "Data" folder as a .csv file.

2. Tweet Preprocessing.ipynb

* This file contains the code to convert the raw tweets into the format required for our classification model.
* Run every cell in the notebook to do this.
* In order to specify which data to preprocess, modify the "dataset" variable to contain either "small" or "large.
* To preprocess topic-based data, set the "creating_topic_dataset" variable to True and the topic variable to "brexit", "covid" or "blm".
* After running all cells, a .npy file will be saved in the "preprocessed_data" folder containing the preprocessed data.

3. Tweet2Vec.ipynb

* This file contains the code to train and test the Tweet2Vec model using the preprocessed data
* Select the dataset using by modifying the "dataset" variable to "large" or "small" and "topic_dataset" to True to use a topic dataset. You can define which topic using the "topic" variable.
* Use the set the "train_model" variable to True to train Tweet2Vec from scratch or False to import the pretrained version.
* The "save_model" variable controls whether to save the model to the "Model" folder.
* Run all cells to output the embeddings for the selected dataset in a .npy file into the "Embeddings Folder.

4. Dimensionality Reduction.ipynb

* This file contains the code to reduce the dimensions of the embeddings and visualise them on a 2d plane.
* Select the required dataset using the "topic_dataset" variable; setting it to True to use a topic dataset. If this is True then modify the "topic" variable to select which topic to use
* Run all cells to reduce the dimensions of these embeddings and to visualise them.
