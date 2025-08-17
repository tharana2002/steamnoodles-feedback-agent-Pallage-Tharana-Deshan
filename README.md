# steamnoodles-feedback-agent-Pallage-Tharana-Deshan
Feedback Response Agent – Automatically responds to customer reviews using sentiment analysis. 

Sentiment Plotting Agent – Generates visualisations of sentiment trends across a selected date range based on user prompts.


Name – Pallage Tharana Deshan

University - NIBm

Year - 3 Year

Summary – Customer Review Response Agent

Automatically analyses restaurant reviews, detects sentiment using DistilBERT, and generates short, polite, and personalised responses via the Groq LLM. Supports future scalability with embedding-based text processing, integrates simple tools, and produces sentiment-aware replies from raw customer input.

Example:

Sentiment: positive

Response: 

"Dear valued customer,
We're thrilled to hear that you enjoyed your dining experience with us! Thank you for taking the time to share your kind words about our food. We're glad you had a great time, and we look forward to serving you again soon.

Best regards,

[Your Restaurant Name]"


Summary – Sentiment Trend Analysis Agent

Processes restaurant review data from CSV, infers sentiment from ratings, filters by date range, aggregates trends over time, and visualises daily sentiment distributions in a stacked bar chart saved as sentiment_trend.png.

Example:

For the date range 2019-03-22 to 2019-03-29, the agent outputs a bar chart showing how customer sentiment varied day by day.


Setup & Run Instructions – Customer Feedback Response Agent

1. Open Google Colab - Go to [Google Colab](https://colab.research.google.com/) and open a new Python notebook.
2. Install Required Dependencies - Run this in the first cell to install all required packages:

!pip install llama-index llama-index-core llama-index-embeddings-huggingface llama-index-llms-groq transformers

3. Add Your Groq API Key - Replace the 'API_KEY' variable in your script with your Groq API key.
4. Upload Script to Colab -

   Option 1: Copy and paste your 'agent_feedback_response.py' content into a Colab cell and run it.
   
   Option 2: Upload your .py file directly:

   from google.colab import file
   files.upload()  # Select your agent_feedback_response.py file

   Then run:
   
   !python agent_feedback_response.py

5. Run Example Review Response Generation- Once the script is loaded and the API key is set, you can test it:

review = "The food was great, but the service was slow."

sentiment = get_sentiment(review)

response = generate_response(review, sentiment)

print(f"Sentiment: {sentiment}")

print(f"Response: {response}")

6. Expected Output

Example:

Sentiment: positive

Response: 

"Dear valued customer,
We're thrilled to hear that you enjoyed your dining experience with us! Thank you for taking the time to share your kind words about our food. We're glad you had a great time, and we look forward to serving you again soon.

Best regards,

[Your Restaurant Name]"


Setup & Run Instructions – Sentiment Plotting Agent

1. Open Google Colab - Go to Google Colab and open a new Python notebook.
2. Install Required Libraries - Run this in the first cell:

   !pip install pandas matplotlib
   
2. Upload the Python Script & CSV File - In Colab, run this to upload your files:

from google.colab import files

Upload agent_sentiment_plot.py,
print("Upload agent_sentiment_plot.py")

files.upload()

Upload Restaurant reviews.csv,

print("Upload Restaurant reviews.csv")

files.upload()

Make sure your CSV file is named exactly: Restaurant reviews.csv

3. Run the Script - After uploading, execute:

   !python agent_sentiment_plot.py
   
4. Check the Output - The script will save the sentiment trend plot to:
   sentiment_trend.png

   To view it directly in Colab:
   
from IPython.display import Image
Image(filename="sentiment_trend.png")

5. Example Run in Colab - If your dataset contains ratings and timestamps, you might run:

from agent_sentiment_plot import plot_sentiment_trends
plot_sentiment_trends("2019-03-22", "2019-03-29")
