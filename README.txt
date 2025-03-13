Newspaper Image Processing with AI

Overview

This project processes newspaper images to identify the positions of photos, extract text, and generate content descriptions using Google Gemini AI. It also provides an AI-powered summary of the news with a political analysis.

Features

Upload and Process Newspaper Image: Users can upload an image of a newspaper.

Photo Position Detection: Identifies and marks positions of images within the newspaper.

Text Extraction: Extracts text content from the newspaper image using AI.

News Analysis: Generates a summary focusing on political consequences and future predictions.

Image Description Generation: Provides AI-generated descriptions for cropped images from the newspaper.

Technologies Used

Google Colab: For running the project in an interactive environment.

Google Gemini AI (gemini-2.0-flash): For AI-driven text extraction and content generation.

Python Libraries:

PIL for image processing

matplotlib for visualization

google.generativeai for AI-based text generation

os for file handling

Installation and Setup

Run the script in Google Colab

Upload a newspaper image when prompted.

Install necessary dependencies (if not installed already):

!pip install google-generativeai

Set up Google Gemini API key:

import google.generativeai as genai
genai.configure(api_key="YOUR_GEMINI_API_KEY")

Run the notebook and follow instructions.

Usage

1. Upload a Newspaper Image

from google.colab import files
uploaded = files.upload()

2. Process the Image

image = Image.open(image_path)

3. Detect Images and Extract Text

response = client.models.generate_content(
    model="gemini-2.0-flash",
    contents=["Extract text from the image", image]
)

4. Analyze News and Generate Summaries

response = client.models.generate_content(
    model="gemini-2.0-flash",
    contents=["Analyze the news article with political consequences and future predictions.", text_content]
)

5. Generate AI-Based Image Descriptions

for image_file in os.listdir(cropped_images_dir):
    image_path = os.path.join(cropped_images_dir, image_file)
    image = Image.open(image_path)
    response = client.models.generate_content(
        model="gemini-2.0-flash",
        contents=["Generate short description for the image", image]
    )

Output

Bounding box-marked images highlighting newspaper photos.

Extracted text saved in extracted_text.txt.

AI-generated summaries of the article.

Descriptions for individual images cropped from the newspaper.

Notes

Ensure the GEMINI_API_KEY is correctly set up.

The model used is gemini-2.0-flash for fast processing.

Future Enhancements

Improve image segmentation for better detection.

Enhance the AI model's contextual analysis for deeper insights.

Implement a UI for easier interaction.

License

This project is for educational and research purposes.
