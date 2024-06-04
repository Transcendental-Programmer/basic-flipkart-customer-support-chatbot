## Basic Flipkart Customer Support Chatbot

This project implements a basic chatbot simulating Flipkart customer support interaction. It leverages Python libraries like NLTK and Keras for natural language processing and machine learning.

### Dependencies

* nltk
* json
* pickle
* numpy
* keras

### Files

* `intents.json`: This file defines the chatbot's intents (customer queries) and corresponding responses in JSON format.
* `words.pkl`: This pickled file stores the vocabulary used to train the model.
* `classes.pkl`: This pickled file stores the list of classified intents (customer query categories).
* `chatbot_model.h5`: This file contains the pre-trained Keras model for the chatbot.

### Usage

**Note:** This project requires the mentioned libraries to be installed.

1. Run the script by typing `python main.py` in your terminal.
2. The message "GO! Bot is running!" indicates the chatbot is ready.
3. Type your customer support query and press enter.
4. The chatbot will analyze your message and provide a relevant response simulating a Flipkart customer support agent.
5. You can continue the conversation by typing new queries.

### Code Breakdown

The provided code snippet demonstrates the core functionalities of the chatbot:

* **Data Loading:**
    * `intents.json` is loaded using `json.loads`.
    * Pickled word list (`words.pkl`) and class list (`classes.pkl`) are loaded using `pickle.load`.
    * The pre-trained model (`chatbot_model.h5`) is loaded using `load_model`.
* **Text Preprocessing:**
    * `clean_up_sentence` tokenizes the sentence and lemmatizes each word for better understanding.
    * `bag_of_words` creates a one-hot encoded representation of the sentence based on the vocabulary. 
* **Prediction:**
    * `predict_class` utilizes the model to predict the most likely class (intent) for the given query.
    * It applies a threshold to filter out predictions with low confidence.
* **Response Generation:**
    * `get_response` retrieves a random response from the predicted intent's list of responses in `intents.json`.
