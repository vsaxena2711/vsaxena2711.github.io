---
title: "📘 Notes from My AI-900 Journey: Azure AI Fundamentals"
date: 2025-03-01
draft: false
---

## 🚀 I Passed the AI-900 Exam!

I’m excited to share that I cleared the **AI-900: Microsoft Azure AI Fundamentals** exam! 🎉  
While preparing, I created a set of personal notes — and I’m sharing them here in the hope that they’ll help others on the same path.

These notes aren’t a complete study guide, but they *are* great for quick reference, revision, and understanding the core concepts you’ll need to know for the exam.

---
## 🧭 Quick Navigation

- [🧠 Fundamental AI Concepts](#-fundamental-ai-concepts)
- [🤖 Fundamentals of Machine Learning](#-fundamentals-of-machine-learning)
- [👁️ Fundamentals of Computer Vision](#-fundamentals-of-computer-vision)
- [👤 Fundamentals of Facial Recognition](#-fundamentals-of-facial-recognition)
- [🔡 Fundamentals of Optical Character Recognition](#-fundamentals-of-optical-character-recognition)
- [📚 Fundamentals of Text Analysis with the Language Service](#-fundamentals-of-text-analysis-with-the-language-service)
- [🗣️ Fundamentals of Conversational Language Understanding](#-fundamentals-of-conversational-language-understanding)
- [🔊 Fundamentals of Azure AI Speech](#-fundamentals-of-azure-ai-speech)
- [📌 Important Topics](#-important-topics)

---
## 🧠 Fundamental AI Concepts

### 📊 Key Workloads of AI

- **Machine Learning**  The foundation of many AI systems. It enables computers to learn from data and make predictions or decisions without being explicitly programmed.
- **Computer Vision**  Enables machines to interpret and process visual information from images or videos.
- **Natural Language Processing (NLP)**  Allows machines to understand, interpret, and generate human language — both spoken and written.
- **Document Intelligence**  Helps process and extract data from structured and unstructured forms and documents.
- **Knowledge Mining**  Extracts useful insights from large volumes of unstructured information and creates a searchable knowledge base.
- **Generative AI**  Focuses on creating new content — such as text, code, or images — using models trained on large datasets.

### 🧪 Machine Learning in Microsoft Azure

Microsoft Azure provides the **Azure Machine Learning service** — a cloud-based platform for building, training, and deploying machine learning models.

#### Authoring Experiences

- **Automated Machine Learning**  Empowers non-experts to build effective machine learning models quickly from their data.
- **Azure Machine Learning Designer**  A no-code, drag-and-drop interface to design machine learning workflows.
- **Data Metric Visualization**  Helps analyze and optimize experiments using built-in visual tools.
- **Notebooks**  Integrated Jupyter Notebooks for writing and running code directly in Azure Machine Learning Studio.

### 👁️ Computer Vision in Microsoft Azure

Computer vision enables AI to interpret the world visually — through images, video, or camera input.

#### Common Computer Vision Models

- **Image Classification** – Classify an image into a predefined category.
- **Object Detection** – Detect and locate objects in images.
- **Semantic Segmentation** – Identify pixel-level boundaries of objects.
- **Image Analysis** – Extract tags, descriptions, and content.
- **Face Detection, Analysis & Recognition** – Recognize or verify individuals.
- **Optical Character Recognition (OCR)** – Read printed or handwritten text.

#### Azure AI Vision Capabilities

- **Image Analysis**  Analyze images and extract descriptions, tags, text, and objects.
- **Face**  Detect facial features, emotions, and perform recognition or verification.
- **OCR (Optical Character Recognition)**  Extract text from scanned documents, handwritten notes, and images.

### 🗣️ Natural Language Processing (NLP)

Natural Language Processing enables software to understand and interact using human language — both written and spoken.

#### What Can NLP Do?

- Analyze and interpret text in documents, emails, and messages.
- Interpret spoken language and generate spoken responses.
- Translate content between different languages.
- Understand intent behind commands and respond appropriately.

#### Azure Services for NLP

- **Azure AI Language** – Analyze sentiment, extract key phrases, detect language, and more.
- **Azure AI Speech** – Transcribe speech to text, synthesize text to speech, translate spoken content.


### 📄 Document Intelligence

Document Intelligence refers to the ability to process and extract structured data from unstructured or semi-structured content like forms, invoices, receipts, and documents.

#### Azure Document Intelligence Capabilities

- **Azure AI Document Intelligence** (formerly Form Recognizer) enables scanning, processing, and extracting text, tables, and key-value pairs from documents like PDFs or images.


### 🔍 Knowledge Mining

Knowledge mining involves extracting meaningful insights from large volumes of unstructured data — such as PDFs, Office docs, and other content — and making that data searchable.

#### Azure Services for Knowledge Mining

- **Azure AI Search** – Combines indexing, natural language processing, and cognitive skills to make unstructured content searchable and insightful.

### ✨ Generative AI

Generative AI enables machines to create content — not just analyze it. This includes:

- Natural language (text)
- Images
- Code
- Audio
- Video

#### Azure Generative AI Capabilities

- **Azure OpenAI Service**  
  Gives access to powerful language models (e.g., GPT-4, Codex, DALL·E) to build intelligent, generative solutions within your applications.

### 🔐 Responsible AI

Building AI responsibly is critical. Microsoft outlines six key principles that guide the ethical development and deployment of AI.

#### Principles of Responsible AI

- **Fairness**  
  AI systems should treat everyone fairly and avoid bias (e.g., gender, race).

- **Reliability and Safety**  
  AI must be tested to operate safely and consistently — especially in critical areas like healthcare or transportation.

- **Privacy and Security**  
  AI should respect data privacy and protect information at every step of its lifecycle.

- **Inclusiveness**  
  AI should be accessible and beneficial to all people, regardless of ability or background.

- **Transparency**  
  AI systems should be understandable, and users should know how decisions are made.

- **Accountability**  
  Humans must remain accountable for AI behavior and ensure ethical compliance.

---
## 🤖 Fundamentals of Machine Learning

### 🧠 Types of Machine Learning

![Types of Machine Learning](/images/ai-notebook/ml-types-diagram.png)


### 🎯 Supervised Machine Learning

Supervised machine learning is a general term for machine learning algorithms in which the training data includes both **feature values** and **known label values**.

These algorithms learn relationships between features and labels from past data, allowing them to predict unknown labels for future data.


#### 📉 Regression

Regression is a type of supervised learning where the label is a **numeric value**.

Examples include:

- The number of ice creams sold on a given day, based on temperature, rainfall, and windspeed.
- The selling price of a property based on square footage, number of bedrooms, and neighborhood stats.
- The fuel efficiency (miles-per-gallon) of a car based on engine size, weight, and dimensions.


#### 🧾 Classification

Classification is another type of supervised learning, where the label is a **category** (class).

##### ✅ Binary Classification

The model predicts one of **two** mutually exclusive outcomes.

Examples:

- Whether a patient is at risk for diabetes based on metrics like weight, glucose level, etc.
- Whether a customer will default on a loan based on income, credit score, etc.
- Whether a marketing campaign will receive a positive response based on demographics and purchase history.

##### 🧩 Multiclass Classification

The model predicts one **class out of multiple possibilities**.

Examples:

- Predicting the **species** of a penguin (Adelie, Gentoo, or Chinstrap) from physical traits.
- Classifying the **genre** of a movie (comedy, horror, romance, etc.) based on its cast, director, and budget.


### 🧬 Unsupervised Machine Learning

Unsupervised machine learning uses data that has **no labels** — only feature values.

These algorithms learn to identify hidden patterns or structures in the data.


#### 🔗 Clustering

The most common form of unsupervised learning is clustering.

It groups observations based on similarities in their features.

Examples:

- Grouping similar flowers based on size, leaf count, and petal count.
- Identifying customer segments based on demographics and shopping behavior.

---
## 👁️ Fundamentals of Computer Vision

### 🤖 Machine Learning for Computer Vision

#### 🧠 Convolutional Neural Networks (CNNs)

One of the most common machine learning model architectures for computer vision is a **convolutional neural network (CNN)**.  
CNNs use filters to extract numeric **feature maps** from images, which are then processed by deep learning layers to generate predictions such as classification labels.

#### 🔀 Transformers and Multi-modal Models

CNNs have traditionally been the foundation of many vision-based models. They're commonly used for **image classification**, and serve as the backbone for more complex tasks like **object detection**, which combines CNN-based feature extraction with region identification to detect and classify multiple objects within an image.

##### 🧩 Transformers

While CNNs have driven most advances in computer vision, another architecture—**transformers**—has transformed natural language processing (NLP). Transformers have enabled large, capable language models, and their adaptability has inspired researchers to explore them for vision tasks too.

##### 🌐 Multi-modal Models

Inspired by transformers in NLP, researchers have developed **multi-modal models** that learn from large volumes of **captioned images** (images with textual descriptions), rather than traditional fixed labels. These models are trained to understand both visual and linguistic data, improving their ability to generalize across modalities.


### 🖼️ Azure AI Vision

You can use either of the following Azure resource types to implement vision AI capabilities:

- **Azure AI Vision**: A dedicated resource for computer vision tasks. Choose this if you want to isolate billing, utilization, and access specifically for vision.
- **Azure AI Services**: A broader resource that includes vision, language, translation, and more. Choose this for multi-service projects where integration and cost management across services is needed.

### 🧪 Analyzing Images with Azure AI Vision

Azure AI Vision supports several out-of-the-box analysis features, including:

- **Optical Character Recognition (OCR)** – Extracts printed or handwritten text from images.
- **Image Captioning** – Generates natural language descriptions of image content.
- **Object Detection** – Identifies and locates thousands of common objects.
- **Visual Tagging** – Assigns descriptive tags to visual elements within the image.

### 🧰 Training Custom Models

#### 🏷️ Image Classification

Use custom image classification to predict **what** category an image belongs to.  
For example, a trained model could identify whether an image contains an apple, banana, or orange.

#### 📦 Object Detection

Object detection models go further by identifying **where** each object is in the image and what it is.  
These models return bounding box coordinates for each object detected.  
You can train object detection models using your own dataset—such as images of fruits—to detect multiple objects in a single image.

---
## 👤 Fundamentals of Facial Recognition

### 🔍 Uses of Face Detection and Analysis

There are many applications for face detection, analysis, and recognition. For example:

- **Security** – Facial recognition can be used in building access control systems and smartphone unlocking mechanisms.
- **Social Media** – Automatically tag friends in photos using facial recognition.
- **Intelligent Monitoring** – In automobiles, detect if the driver is distracted, drowsy, or not looking at the road.
- **Advertising** – Analyze faces to tailor ads to the appropriate demographic audience.
- **Missing Persons** – Use public surveillance systems to identify missing individuals.
- **Identity Validation** – Helpful at border entry kiosks using special access permits.

### 🧠 Understand Face Analysis

Face detection involves identifying regions in an image that contain a human face by returning **bounding box coordinates**.

With **face analysis**, facial landmarks such as the nose, eyes, eyebrows, and lips are identified and used to derive insights or feed downstream machine learning models.

### 🧬 Facial Recognition

Facial recognition takes facial analysis a step further. It involves training a machine learning model with **multiple images** of a known individual so that the model can later **identify them in unseen images**. This enables accurate identity matching across image datasets.

### ⚙️ Get Started with Face Analysis on Azure

Microsoft Azure offers various services for face detection and analysis:

- **Azure AI Vision** – Detects faces and returns basic face attributes such as bounding boxes.
- **Azure AI Video Indexer** – Identifies faces in video content using advanced vision capabilities.
- **Azure AI Face** – Offers pre-trained models for detecting, analyzing, and recognizing faces in still images.

### 🧾 Face Service Attributes

The Azure Face service can return the coordinates of human faces and provide additional attributes, including:

- **Accessories** – Identifies glasses, masks, headwear, etc., along with a confidence score.
- **Blur** – Measures how blurry the face appears.
- **Exposure** – Analyzes underexposure or overexposure on the detected face.
- **Glasses** – Detects if the person is wearing glasses.
- **Head Pose** – Captures 3D orientation of the head.
- **Mask** – Indicates whether the person is wearing a mask.
- **Noise** – Measures image graininess which may affect face clarity.
- **Occlusion** – Detects if the face is partially covered or blocked by other objects.

### 🔧 Azure Resources for Face

To use the Face service in Azure, you can create one of the following resource types:

- **Face** – A dedicated resource for Azure AI Face, best if you want isolated billing and usage tracking.
- **Azure AI Services** – A consolidated resource that supports Face along with other services like Language, Content Safety, and more.

---
## 🔡 Fundamentals of Optical Character Recognition

### 🧠 Azure AI Vision's OCR Engine

The **Azure AI Vision** service enables the extraction of machine-readable text from images using its powerful **Read API**. This OCR engine supports images, PDFs, and TIFF files, and is optimized for general, non-document images — making it ideal for user-facing applications that involve text recognition.

When you call the **Read API**, it returns results in a structured hierarchy:

- **Pages** – Each page of text, along with page size and orientation.
- **Lines** – Lines of text found on each page.
- **Words** – Words within the lines, including the bounding box and text content.

### 🚀 Get Started with Vision Studio on Azure

To begin using **Azure AI Vision**, you’ll need to create a resource in your Azure subscription. You have two options:

- **Azure AI Vision** – A dedicated resource for vision services. Best suited if you're only using Vision and want separate tracking of costs and usage.
- **Azure AI Services** – A broader resource that includes Vision, Language, Speech, and other services. Ideal for managing multiple AI services under a single umbrella.
---
## 📚 Fundamentals of Text Analysis with the Language Service

### 💬 Introduction to NLP and Azure AI Language

Natural Language Processing (NLP) enables computer systems to interpret written or spoken language in a way that’s similar to how humans do. **Text analysis** is a branch of NLP that focuses on extracting meaningful insights from unstructured text.

**Azure AI Language** is a cloud-based service that provides features for text understanding — such as sentiment analysis, key phrase extraction, summarization, and more.

### 🔍 Understand Text Analytics

#### 🧩 Tokenization

The first step in analyzing text is breaking it into smaller components called **tokens**. Tokens can be individual words, punctuation marks, or combinations.

Example phrase: `"we choose to go to the moon"`

Tokenized:
1. we  
2. choose  
3. to  
4. go  
5. the  
6. moon  

Token sequence: `[1, 2, 3, 4, 3, 5, 6]`

#### 📈 Frequency Analysis

After tokenizing, you can count how often each token appears. Common terms (excluding stop words like “a” or “the”) often reveal the document’s subject.  
For example:  
- Frequent words: `new`, `go`, `space`, `moon`  
- Common bi-gram: `the moon`  
The context implies that the subject is space travel.

#### 🤖 Machine Learning for Text Classification

You can train machine learning models to classify text using algorithms like **logistic regression**.  
Use case: **Sentiment analysis**

Labeled examples:
- "The food and service were both great" → 1 (positive)  
- "A really terrible experience" → 0 (negative)  
- "Mmm! tasty food and a fun vibe" → 1 (positive)  
- "Slow service and substandard food" → 0 (negative)

#### 🧠 Semantic Language Models

Modern NLP leverages **semantic embeddings**, which encode tokens as numeric vectors. These vector-based representations help models understand meaning and relationships between words.

### 🚀 Get Started with Text Analysis in Azure

**Azure AI Language** supports a variety of NLP capabilities:

- **Named Entity Recognition (NER)** – Identifies people, places, events, and more. Customizable categories are also supported.
- **Entity Linking** – Matches known entities and links them (e.g., to Wikipedia).
- **PII Detection** – Identifies sensitive personal or health-related info.
- **Language Detection** – Returns language name (`English`), code (`en`), and confidence score.
- **Sentiment Analysis** – Labels sentences as positive, neutral, or negative.
- **Summarization** – Condenses long text to highlight core insights.
- **Key Phrase Extraction** – Extracts essential points from large text bodies.

### 🧾 Entity Recognition and Linking

Submit unstructured text and get back identified **entities** — categorized items like people, locations, or dates.

### 🌍 Language Detection

Azure detects:
- Language name (e.g., English)
- ISO 639-1 code (e.g., `en`)
- Confidence score

Useful for multilingual applications and localization tasks.

### ❤️ Sentiment Analysis and Opinion Mining

Azure’s sentiment analysis returns:
- Sentiment label (positive, neutral, or negative)
- Confidence scores
- Sentence-level granularity

Used in analyzing reviews, social media posts, support tickets, etc.

### ✨ Key Phrase Extraction

Summarizes the main points of a document by listing essential phrases.  
For example, from many restaurant reviews, Azure AI Language can help extract:
- `Great service`
- `Delicious food`
- `Long wait time`
---
## 🗣️ Fundamentals of Conversational Language Understanding

### 🧠 Describe Conversational Language Understanding

Conversational language understanding enables applications to interpret user input in natural language conversations. It focuses on three main concepts: **utterances**, **entities**, and **intents**.

#### 💬 Utterances

An **utterance** is something a user might say.

Examples:
- "Switch the fan on."
- "Turn on the light."

These represent inputs the system should understand and interpret meaningfully.

#### 🧩 Entities

An **entity** is a specific item or concept mentioned in an utterance.

In the examples above:
- `"fan"` and `"light"` are entities — both are types of **device**.

Entities help the system identify what the user is talking about.

#### 🎯 Intents

An **intent** represents the goal or purpose of an utterance.

Both examples aim to **turn a device on**, so the intent might be labeled as `TurnOn`.

Your conversational model groups related utterances under defined intents and identifies entities within them.

> 🧠 Think of it like this:  
> "Turn on the fan." → Intent = `TurnOn`, Entity = `fan`

### 🛠️ Building a Conversational Model in Azure

To build a conversational AI model in Azure, you define:
- **Entities** (e.g., device names)
- **Intents** (e.g., TurnOn, TurnOff)
- **Utterances** to train the model

Azure uses these to train your model to understand user inputs.

You might build models for various scenarios such as:
- Turning devices on/off
- Setting reminders
- Booking appointments

### 🧰 Azure Resources for Conversational AI

To use conversational understanding in Azure, you need a resource:

- **Azure AI Language**  
  Best for authoring and predicting. Offers a complete development and deployment experience.

- **Azure AI Services**  
  A general-purpose resource. Can be used for **prediction only**.

### ✍️ Authoring the Model

Once you have a resource, you define:
- **Intents** (like `TurnOn`, `TurnOff`)
- **Entities** (like `fan`, `light`)
- **Utterances** (example user phrases)

Azure also offers **prebuilt domains** — collections of pre-defined intents and entities to help you get started.

You can use these or create custom ones tailored to your application.

### 🏋️ Training the Model

Training uses your sample utterances to "teach" the model how to match user input to intents and entities.

For example:
- Input: `"Switch on the heater"`
- Model Prediction: `Intent = TurnOn`, `Entity = heater`

Training helps the model generalize so it can understand variations in language.

### 🚀 Predicting with the Model

After testing and validating your model, you publish it to a **prediction resource**.

Client applications (chatbots, mobile apps, websites) then:
- Send user input to the prediction endpoint
- Receive a response containing:
  - The **predicted intent**
  - The **identified entities**

Based on the prediction, the app can then perform an appropriate action.

Example:
```json
{
  "intent": "TurnOn",
  "entities": ["light"]
}
```
---
## 🔊 Fundamentals of Azure AI Speech

AI speech capabilities allow us to interact with technology through voice — whether that’s managing home systems, asking questions aloud, generating captions, or receiving spoken responses.

To enable this interaction, AI systems must support two core capabilities:

- **Speech Recognition** – Understanding spoken language and converting it into text.
- **Speech Synthesis** – Generating spoken output from text.

Azure provides both through the **Azure AI Speech** service, supporting prebuilt and custom models for use cases like real-time transcription, custom voice creation, and more.

### 🧠 Understand Speech Recognition and Synthesis

#### 🗣️ Speech Recognition

Speech recognition converts spoken input (live or recorded) into machine-readable data, typically in the form of text.

It involves:
- **Acoustic Models** – Convert the audio signal into **phonemes** (basic sound units).
- **Language Models** – Map phonemes to words using statistical algorithms.

Common use cases:
- Live captions and subtitles for videos
- Automated meeting transcripts
- Dictation tools
- Voice command interfaces

#### 🗣️ Speech Synthesis

Speech synthesis, or **Text-to-Speech (TTS)**, generates spoken output from text.

To synthesize speech, the system:
- Tokenizes text into words
- Assigns phonetic values to each word
- Breaks phonemes into phrases or sentences
- Generates audio with desired **voice**, **pitch**, **volume**, and **speed**

Use cases include:
- Voice assistants and bots
- Telephone IVRs
- Email readers for accessibility
- Public announcement systems

### 🚀 Get Started with Speech on Azure

Azure’s **AI Speech service** provides both recognition and synthesis via the following APIs:

- **Speech to Text API** – Convert spoken language to written text.
- **Text to Speech API** – Convert written text to spoken voice output.

#### 🧰 Azure Resource Options

To use Azure AI Speech, create one of the following resources:

- **Speech Resource** – For projects focused solely on speech capabilities.
- **Azure AI Services Resource** – For multi-service solutions using Speech, Language, Vision, etc.


### 🎤 Speech to Text API

#### 🔴 Real-time Transcription

Transcribe audio as it happens — ideal for live presentations, demos, or accessibility scenarios.

#### 📦 Batch Transcription

Upload audio files (e.g., from file shares or Azure Storage via SAS URI) and receive transcription results asynchronously.


### 🗣️ Text to Speech API

With the **Text to Speech API**, you can specify custom **voices**, making your application sound unique and engaging.

Applications include:
- Responding to user queries
- Interactive phone systems
- Accessibility tools (e.g., email reading)
- Smart environments with vocal output

---

## 📌 Important Topics

### 🧮 Binary Classification Evaluation Metrics

The first step in evaluating a binary classification model is creating a **confusion matrix**, comparing predicted labels (ŷ) with actual labels (y):

| Actual / Predicted | 0 (Negative) | 1 (Positive) |
|--------------------|--------------|--------------|
| 0 (Negative)       | TN           | FP           |
| 1 (Positive)       | FN           | TP           |

Where:
- **TN** – True Negative
- **FP** – False Positive
- **FN** – False Negative
- **TP** – True Positive

#### ✅ Accuracy
Proportion of total predictions that were correct:  
**(TP + TN) / (TP + TN + FP + FN)**

#### 📢 Recall (Sensitivity)
Proportion of actual positives correctly identified:  
**TP / (TP + FN)**

#### 🎯 Precision
Proportion of predicted positives that are actually positive:  
**TP / (TP + FP)**

#### ⚖️ F1-Score
Harmonic mean of Precision and Recall:  
**(2 × Precision × Recall) / (Precision + Recall)**

#### 📈 Area Under the Curve (AUC)
AUC measures performance by plotting **True Positive Rate (TPR)** against **False Positive Rate (FPR)**:
- TPR = TP / (TP + FN)
- FPR = FP / (FP + TN)
AUC is **threshold-invariant**, meaning it evaluates model quality regardless of threshold used.

---

### 📋 Metrics for Classification Models

- **Accuracy** – Proportion of all correct predictions.
- **Precision** – TP / (TP + FP)
- **Recall** – TP / (TP + FN)
- **F1 Score** – Weighted average of precision and recall.
- **AUC** – Area under the ROC curve.

---

### 📊 Metrics for Regression Models

Used to estimate the **amount of error** between predicted and actual values.

- **Mean Absolute Error (MAE)** – Average of absolute differences.
- **Root Mean Squared Error (RMSE)** – Square root of average squared errors.
- **Relative Absolute Error (RAE)** – Ratio of total absolute error to the total absolute error of the mean.
- **Relative Squared Error (RSE)** – Ratio of squared error to the total squared error of the mean.
- **R² (Coefficient of Determination)** – Predictive power; 0 = no predictive value, 1 = perfect fit.

---

### 📌 Metrics for Clustering Models

Used to measure the compactness and separation of clusters:

- **Average Distance to Other Center** – How far each point in a cluster is from other cluster centroids.
- **Average Distance to Cluster Center** – Closeness of points to their own cluster center.
- **Maximal Distance to Cluster Center** – Furthest distance within the cluster.
- **Number of Points** – Count of points assigned to each cluster.
- **Combined Evaluation Score** – Overall average performance across all clusters.

---

### 🧠 Text Analytics Capabilities

- **Sentiment Analysis** – Detects sentiment as *Positive*, *Neutral*, or *Negative*.
- **Key Phrase Extraction** – Pulls main ideas from unstructured text.
- **Entity Recognition** – Identifies people, places, organizations, etc.
- **Language Detection** – Identifies the language of given text.

---

### 🧱 Entity Types in LUIS (Language Understanding)

While authoring a LUIS application, you can define entities as:

- **Machine-Learned** – AI learns how to extract them from examples.
- **List** – Predefined list of possible values.
- **RegEx** – Match patterns with regular expressions.
- **Pattern.any** – Wildcard-based matching.

---

### 🔁 Four Steps of Data Transformation

- **Feature Selection** – Selecting relevant variables.
- **Removing Outliers** – Cleaning data for better generalization.
- **Impute Missing Values** – Filling in missing data points.
- **Normalize Numeric Values** – Scaling values to a standard range.

---

### 💬 Sentiment Analysis Categories

- **Positive** – Expresses joy, satisfaction, excitement, etc.
- **Neutral** – Objective or factual; no strong emotion.
- **Negative** – Expresses disappointment, frustration, or dissatisfaction.

