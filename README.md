# How ML and AI can help community events planning, execution and analysis

Author: Alfredo Morresi

# EVERYTHING IS STILL IN PROGRESS


## Prework
- Create a GCP Project
- Enable Vertex AI API
- Enable Cloud Assistant API, to ask questions in the console
- Request access to Imagen 2 via https://docs.google.com/forms/d/1cqt9padvfMgqn23W5FMPTqh7bW1KLkEOsC5G6uC-uuM/viewform

### Ollama
https://github.com/ollama/ollama
https://ollama.com/  
brew iinstall --cask ollama
https://ollama.com/library, and insall gemma:7b (ollama run gemma:7b)
http://localhost:11434/

ollama pull gemma:2b
ollama pull nomic-embed-text



## A word on prompting

Prompt engineering is an art. Practive it without fear of making mistakes!

### Some suggestions
1. Clearly communicate what content or information is most important. Focus on telling the model exactly what you want it to do rather than telling it what not to do.
1. Structure the prompt:
    - Defining the role if using one. For example, You are an experienced UX designer at a top tech company
    - Include context and input data
    - Provide the instructions to the model
    - Add example(s) if you are using them
1. Use specific, varied examples to help the model narrow its focus and generate more accurate results.
1. Use constraints to limit the scope of the model's output. For example, Make sure to limit your response to 3 sentences.. This can help avoid meandering away from the instructions into factual inaccuracies.
1. Break down complex tasks into a sequence of simpler prompts.
1. Instruct the model to evaluate or check its own responses before producing them. Some examples are: Rate your own work on a scale of 1-10 or Do you think this is correct? Why?.
1. When prompting the model to gather information or explain a topic, encourage it to cite its source material.
1. Consider that open-ended question-answering prompts tend to work better than those that restrict model generation. In [this paper](https://openreview.net/forum?id=bhUPJnS2g0X), the researchers found the prompt Who went to the park? outperformed John went to the park. True or False?.

### General considerations
- It's common for models to hallucinate citations and source links. Expect to verify whether the output is factually accurate.
- Human review is a large part of the LLM improvement process. Do not enter sensitive or personal information.
- And perhaps most important: Be creative! LLMs and prompt engineering are still in their infancy, and evolving every day. Who knows, you might even discover the newest emergent ability.

Suggestions on prompting? https://ai.google.dev/examples

<br/>

## TODO - Introduce your community to the rest of the world

Steps
- Gather some images of your community activities.
  - If not available, visit https://developers.google.com/community/gdg and download the 3 pictures in the page ([image1](https://developers.googleblog.com/2022/08/a-conversation-with-android-developer-and-community-builder-ceren-tunay.html), [image2](https://developers.google.com/static/community/gdg/images/bailey_480.jpeg), [image3](https://developers.google.com/static/community/gdg/images/lesego-and-simon_480.jpeg))
- Open Vertex AI Multimodal


Prompts
```
These pictures show different activities organized by tech communitis. Write an engaging blog post based on these pictures. It should talk about the importance of tech communities, providing examples of their activities taken from these pictures. 

Write an engaging blog post based on these pictures. It should talk about the importance of tech communities, using activities represented in these pictures. 
```

Try the output differences using "Gemini Experimental" vs "Gemini-1.0-pro-vision.001".  

## Planning your event
TODO


## Speaker selection
https://github.com/VinciGit00/Scrapegraph-ai


## Preparing the event

### TODO - Generate event description

Generate some description of what your community does
```
Write a short, engaging blog post based on these picture. It should include a description of the meal in the photo and talk about my journey meal prepping. 
```

Create event description
Mix something about your community, something about the topics of the event and ask:

```
You are a newspaper reporter describing quantum entanglement as breaking news. What is the catchy headline?
```

Then the even title


Prompts to try
- You're a social media manager. You need to write social-media tailored prompt to advertise an event about AngularJS and a new library to create responsive websites.
Create different snippets of text
- The more context you give to Gemini, the better it can understand your request and generate a useful response.
  - Instead of..."Write about a sales job.", try this..."Write a job description for a [job title], including the required skills and experience, as well as a summary of [company name] and the position."
  - Instead of..."Create project plan.", try this..."Create a project plan for the launch of a brand new product. The timeframe should be from now until June 2024."

### TODO - Generate event creativity

Resouces
- https://cloud.google.com/vertex-ai/generative-ai/docs/image/overview?hl=en
- https://www.youtube.com/watch?v=pN-RTBq6i3I
- https://cloud.google.com/blog/products/ai-machine-learning/imagen-2-on-vertex-ai-is-now-generally-available

Steps
- In the Google Cloud console, go to the Vertex AI Studio page
- Click Vision Powered by Imagen 
- Click "Generate" to write your prompt


In case you wanna use a different model
- In the Google Cloud console, go to the Vertex AI Model Garden page
- Select StableDiffusion or other models


### Accessibility for your images
Steps
- In the Google Cloud console, go to the Vertex AI Studio page
- Upload images for your event
- Press "Generate caption" to get the text to add in the ALT attribute of the image


### TODO - Generate voice for podcasts and other media
TODO

## Reporting
### Count your attendees

Resources
- https://cloud.google.com/vertex-ai/generative-ai/docs/start/quickstarts/quickstart-multimodal?hl=en

Steps
- Take a photo of the event attendees
- In the Google Cloud console, go to the Vertex AI Studio page
- Click Multimodal
- Select model: gemini-1.0-pro-vision-001 ([more on models](https://cloud.google.com/vertex-ai/generative-ai/docs/learn/models?hl=en))
- Upload the picture of the attendees
- Prompt: "How many people there are in the picture?"
- Submit the prompt by clicking Submit.
- Enjoy an automatic count of the number of attendees


## At the event

### TODO - Ask questions to the speaker
- Prompt Gemini
  - Instead of..."Marketing talking points.", try this..."Give me 12 thoughtful questions to ask a Chief Marketing Officer on their strategy for 2024."
  - As usual, If you want Gemini to perform several related tasks, break them apart into separate prompts. This helps the AI understand the task and provide useful responses.


## Attendees Analysis

Resources
- 

Steps
- Open Gemini
- TODO: get your answers from Bevy
- Ask it if it will summarize a set of data, giving as much specifics as possible (i.e. please summarize this survey data from an internal reading challenge). Paste the data and press enter.
  - One challenge I came across though was that sometimes Gemini would hallucinate and I had to try different prompts and ways to verify if how it categorises the responses is legit. Asking to illustrate data categorisation with quotes from respondents proved to work the best. 





## Ideas to explore
- https://github.com/trending
- https://dev.events/
- https://www.gdeltproject.org/about.html

Conferences
- https://www.wearedevelopers.com/
- https://ng-conf.org/speakers/
- https://nyc24.devrelcon.dev/
- https://conferences.codemotion.com/milan2023-live/agenda/


- Deploy stablediffusion via VertexAI (also Imagen)
- HuggingFace checkpoint to call for getting images
  - Deploy solution to HF so people can visit it

At the event
- Agent to get the pizza
- Manage the logistic
- food and drinks
- do opening for the event (speaker, opening, generate text)
- feedback form generation (based on the talks and general question)
- thank you notes for the attendees
- resume of the talk points
- record the video and parse it
- Q&A the video with Pro windows
- blogpost about the topic