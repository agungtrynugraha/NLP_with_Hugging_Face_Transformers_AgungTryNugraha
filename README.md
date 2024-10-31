Natural Language Processing with Hugging Face Transformers
📖 Project Overview
This project explores multiple functionalities of Hugging Face Transformers, focusing on tasks like sentiment analysis, summarization, and translation. These models leverage state-of-the-art deep learning architectures to perform complex language processing tasks with minimal setup.

Each section in this repository demonstrates a unique NLP application, providing a foundational understanding of how to implement these capabilities and apply them in real-world projects.

🚀 Features & Functionalities
Sentiment Analysis - Classify the sentiment of a sentence as positive or negative, including a confidence score.
Summarization - Generate concise summaries from longer texts to capture the main ideas.
Translation - Translate text from Indonesian to English (ID ➔ EN) with high accuracy.
📂 Code Walkthrough

from transformers import pipeline
classifier = pipeline("sentiment-analysis")
# List of sentences to analyze
sentences = [
    "The model was so great! I think I'm going to choose this.",
    "I'm not satisfied with the product at all.",
    "The experience was amazing, definitely would recommend!",
]
# Analyze sentiment for each sentence
for sentence in sentences:
    result = classifier(sentence)[0]
    print(f"Sentence: {sentence}")
    print(f"Sentiment: {result['label']} (Confidence: {result['score']:.2f})\n")


from transformers import pipeline
summarizer = pipeline("summarization")
text = """
    America has changed dramatically during recent years. Not only has the number of
    graduates in traditional engineering disciplines such as mechanical, civil,
    electrical, chemical, and aeronautical engineering declined, but in most of
    the premier American universities engineering curricula now concentrate on
    and encourage largely the study of engineering science.
"""
# Generate summary
summary = summarizer(text, max_length=100, min_length=30, do_sample=False)[0]['summary_text']
print("Summary:")
print(summary)


from transformers import pipeline
translator = pipeline("translation", model="Helsinki-NLP/opus-mt-id-en")
texts_to_translate = [
    "aku suka menggambar",
    "selamat pagi, semoga harimu menyenangkan",
    "makanan favorit saya adalah nasi goreng",
]
# Translate each text
for text in texts_to_translate:
    result = translator(text)[0]
    print(f"Original Text: {text}")
    print(f"Translation: {result['translation_text']}\n")

🔍 Analysis & Insights
Ease of Use: Hugging Face’s pipeline abstracts complex model setups, allowing you to use sophisticated NLP models with minimal code.
Customizability: By adjusting parameters, you can modify outputs for specific use cases (e.g., controlling summary length or translation accuracy).
Real-World Application: These models can be integrated into web applications, chatbots, or used for text analysis in various industries, from e-commerce sentiment analysis to cross-language communication tools.
💡 Usage

🌐 References
Hugging Face Transformers Documentation
Model Hub for Pretrained Models
🏆 Conclusion
This repository demonstrates essential NLP techniques using Hugging Face Transformers, providing robust solutions for sentiment analysis, text summarization, and translation. These tools lay the groundwork for scalable, language-processing applications suitable for various modern business needs.

Happy Coding! 🎉