# NLP
What is NLP? 
- How to deal with text data?

What is Data Science?
- Getting meaning out of data
- Using data to make decisions

Programming: 
- Data: pandas, sklearn, re
- NLP: nltk, TextBlob, gensim

Math & Stats:
- Clean: corpus, document-term matrix
- EDA: word counts
- NLP: sentiment analysis, topic modelling, text generation

Communication:
- Design:  scope, visulaize, extract insights
- Domain: expertise


Data Science Workflow:
1. Start with a question 
    - Goal: What makes Ali Wongs' comedy routine stand out?
2. Get & Clean the data 
    - Input: "How is Ali Wong different?"
            - Get: 
            - Domain expertise needed
            - Where are we going to get this data? scraps from the loft
            - How much data should we get? 
            - Which comedians? imdb (adjust the filter to get 10 comedians)
            - What time range? last 5 years
        - Data Gathering:
            - Web Scraping
                - Requests
                    - Formal: Make HTTP requests
                    - Simple: Get info from a website
                - Beautiful Soup
                    - Formal: Parse HTML documents
                    - Simple: Extract parts of a website
            - Saving Python Data:
                - Pickle
                    - Formal: Serialize Python objects
                    - Simple: Save data for later       
                    <br/>

        - Data Cleaning-format:
            1. Format#1 - Corpus
                 - a collection of texts --> We can get this from pandas dataframe
            2. Format#2 - Document-Term matrix
                 - Clean Text --> remove excess, unnecessary parts of the text
                 - Tokenize Text --> split the text into smaller pieces
                 - Document-Text Matrix - put into a matrix so a machine can read it
            3. Common data cleaning steps:
                - Make tex
                - Remove punctuation --> re: Python libraries for regular expression
                - Lowercase letters
                - Remove numbers
                - Tokenization --> You can filter stop words
     - Ouput: Clean, organized data in standard format 
  
  
3. Perform EDA
    - **Input:** a corpus and a document-term matrix 
    - **EDA:** Summarize the main characteristics of the data set 
        - **Data:** Determine the format of the raw data which will need to start
        - **Aggregate:** Figure out how to aggregate the data
        - **Visualize:** Find the best way to visualize the data
        - **Insights:** Extract some key takeways from the visualizations
    - **Output:** figure out the main trends in the data and if it make sense
4. Apply Techniques
    - **Input:** clean data, plus we have verified that the data makes sense
    - **NLP Techniques:** advanced analysis techniques, in this case, they are specifically designed for text data
    - **Output:** additional insights about our data to help us answer our question, "how is Ali Wong different?"
    
      ### 4.1 Sentimental Analysis
      - **Input:** A corpus. The reason we are not using the document-term matrix here is because order matters. "great" = positive. "not great" = negative.
      - **TextBlob:** 
          - TextBlob is a Python library that is built on top of **nltk**. It's easier to use and provides some additional functionality, such as rules-based sentiment scores.
           - TextBlob finds all of the words and phrases that it can assign a polarity and subjectivity to, and **averages** all of them together
           - This rules-based implementation is a knowledge-based technique. There are also statistical methods out there such as **Naive Bayes**.
      - **Output:** For each comedian, we will give them a sentiment score (how positve/negative are they) and a subjectively score (how opionionated are they). 

      ### 4.2 Topic Modeling
      - **Input:** A document-term matrix. Each topic will consist of a set of wprds where order does not matter, so we are going to start with the bag of words format.
      - **genism:** genism is a Python toolkit built by Radim Rehurek specifically for topic modeling. We are going to a popular topic modeling technique called Latent Dirichlet Allocation (LDA). We are also going to use **nltk** for some parts-of-speech tagging.
      - **Output:** Our goal is to find themes across various comedy routines, and see which comedians tend to talk about which themes.

      #### Latent Dirichlet Allocation
      Latent -- > hidden <br>
      Dirichlet --> types of probability distribution

      #### How LDA works?
      - **Goal:** - You want LDA to learn the topic mix in each document, and the word mix in each topic
      - **Input:** - Document-Term Matrix, number of topics, number of iterations
      - genism will go through the process of finding the best word idstribution for each topic and best topic distribution for each document.
      - **Output:** *The top words in each topic*. It is your job as a human to interpret this and see if the results makes sense. If not, try altering the parameters - terms in the document-term matrix, number of topics, number of iterations, etc, *Stop when the topics make sense*.
      - This is a probabilisatic approach to topic modelling. There are also matriz factorization techniques for topic modeling such as **Latent Semantic Indexing (LSI)** and **Non-Negative Matrix Factorization (NMF)**

5. Share Insights
               

