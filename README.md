# How GenAI can help community events planning, execution and analysis

Author: [Alfredo Morresi](https://rainbowbreeze.it)


As a community manager, are you tired of juggling event details and missing out on creative inspiration?  
Here some practical strategies to leverage GenAI-powered tools for community managers, and optimize the entire event planning process. Tips to help with creative asset and marketing material creation, session topic selection, survey analysis, attendee data insights, and more.

Do you have your "magic tips" to share? Pull requests are welcome!


<br/>

## A word on prompting

Prompt engineering is an art. Practive it without fear of making mistakes!

### Some suggestions
1. Clearly communicate what content or information is most important. Focus on telling the model exactly what you want it to do rather than telling it what not to do.
1. Structure the prompt:
    - Defining the **role** if using one. For example, You are an experienced UX designer at a top tech company
    - Include context and input data
    - Provide the instructions to the model
    - Add example(s) if you are using them
1. Use specific, varied **examples** to help the model narrow its focus and generate more accurate results.
1. Use **constraints** to limit the scope of the model's output. For example, Make sure to limit your response to 3 sentences.. This can help avoid meandering away from the instructions into factual inaccuracies.
1. Break down complex tasks into a **sequence** of simpler prompts.
1. Instruct the model to **evaluate or check** its own responses before producing them. Some examples are: Rate your own work on a scale of 1-10 or Do you think this is correct? Why?.
1. When prompting the model to gather information or explain a topic, encourage it to cite its **source material**.
1. Consider that open-ended question-answering prompts tend to work better than those that restrict model generation. In [this paper](https://openreview.net/forum?id=bhUPJnS2g0X), the researchers found the prompt Who went to the park? outperformed John went to the park. True or False?.
1. If one-shot prompting doesn't work, break down the process in multiple steps, create a specialized **agent** to take care of each step, and chain the output of an agent as the input for the next one, to arrive to the desired results.

### General considerations
- For the most part, Gemini and LLMs may be accurate, but they are prone to errors, so you might want to take the information with a pinch of salt.
- Human review is a large part of the LLM improvement process. Do not enter sensitive or personal information.
- And perhaps most important: Be creative! LLMs and prompt engineering are still in their infancy, and evolving every day. Who knows, you might even discover the newest emergent ability.

Suggestions on prompting? https://ai.google.dev/examples


<br/>

## What you need to know
In order to try the different suggestions, a way to access [Gemini mulltimodal](https://cloud.google.com/vertex-ai/generative-ai/docs/multimodal/overview) capabilities is required.
- [Google AI Studio UI](https://ai.google.dev/)
  - Free to use to test the different prompts
  - [List of available countries](https://ai.google.dev/gemini-api/docs/available-regions)
  - TODO: link to a YouTube video
- [Vertex AI Studio Multimodal](https://cloud.google.com/generative-ai-studio)
  - Setup a GCP account and project
  - Open [Vertex AI Studio](https://console.cloud.google.com/vertex-ai/generative) homepage
    - Open "Multimodal Home"
    - Select "Prompt design (single turn)" or open one of the Sample prompts
  - TODO: link to a YouTube video
- [Gemini app](https://gemini.google.com/)
  - Open [Gemini app](https://gemini.google.com/)
    - Free usage for the basic model
    - To use the Gemini Advanced model, a [Google One AI Premium plan](https://one.google.com/explore-plan/gemini-advanced) has to be activated (free for the first 2 months)
  - TODO: link to a YouTube video
- Other options
  - [Vertex AI Studio CLI](https://cloud.google.com/vertex-ai/docs/start/cloud-environment)


<br/>

## Introduce the community to the world

### Write an intro text to present the community
The community landing page is an important showcase to "tell the why and the how" of the community, and attract new members. How to capture its true essence and put it into words? For example, using footage of past community experiences.

After gathering some pictures of past events, access Vertex AI Studio Multimodal, select the "_Gemini 1.5 Pro"_ model, upload the images and prompt:
```
You are a content writer and you want to write an engaging blog post to present a community and its activities, based on the uploaded pictures.
It should talk about the importance of tech communities, providing examples of their activities taken from these pictures, and invite reader to join the community events to learn something new about Google technologies.
``` 

Alternatively, selecting "Gemini 1.0 Pro Vision", prompt:
``` 
The uploaded pictures provide examples of activities run by a community called "GDG Rainbow". You are an experienced content writer and want to write a short and engaging blogpost to talk about this community, present it to the audience and provide reasons why the reader cannot miss events organized by GDG Rainbow. Put emphasis on the learning opportunities offered on Google technologies.
``` 

Things to try:
- Different variation of the output can be obtained changing temperature parameter, specifying style of the text, etc.
- The more context you give to Gemini, the better it can understand your request and generate a useful response.
  - Instead of..."Write about a sales job.", try this..."Write a job description for a [job title], including the required skills and experience, as well as a summary of [company name] and the position."
  - Instead of..."Create project plan.", try this..."Create a project plan for the launch of a brand new product. The timeframe should be from now until June 2024."
- [Gemini app](https://gemini.google.com/) can process only one picture at time. Vertex AI Studio, instead, can take more images as input.
- If there are no past pictures to show, what about using the ones from "twin" communuties?


<br/>

## Organizing an event

### Generate event title and description
Once the topic of the session is decided, prompts can help generating session titles and descriptions to get inspired from. 

In Gemini app, prompt:
```
You're a community manager. You have organized a speaker session about how to build the first GenAI powered Android app, using Vertex AI.
The event will be hosted in SkillsMatter tech space, on May 24 from 6:00 to 8:00pm.
Write a text to present the event to a potential audience, including the event agenda.
```

Let's add some event-specific context:
```
You're a community manager. You have organized a speaker session about how to build the first GenAI powered Android app, using Vertex AI.
The event will be hosted in SkillsMatter tech space, on May 24 from 6:00 to 8:00pm.
Write a text to present the event to a potential audience, including the event agenda.
Alfredo Morresi will be the speaker.
Focus on the unique aspects of the event: it's the first one in the Pavia area about this topic, the speaker is a well-known expert on Android add development, the Q&A session will give the audience an opportunity to ask about real-world experience in developing this kind of mobile app.
```

Now, let's create some social-media snippets:
```
You're a social media manager. You need to write a text tailoed for X and LinkedIn social media to advertise a speaker session about how to build the first GenAI powered Android app, using Vertex AI.
List hashtags to use.
```

Too hyperbolic? Let's fix it:
```
You're a social media manager. You need to write a text tailoer for X and LinkedIn social media to advertise a speaker session about how to build the first GenAI powered Android app, using Vertex AI.
List hashtags to use.
The post targets a tech audience, so avoid all the marketing buzz.
```


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


<br/>

## At the event

### Generate question for the Q&A session with the speaker
It may happen that no one wants to break the ice during a Q&A session making the first question. Hence, having a list of few ready-made ones to fill that awkward silence can be helpful.  
If the speaker provides a presentation in advance, it's possible to get them using [Vertex AI Studio Multimodal](https://cloud.google.com/vertex-ai/generative-ai/docs/multimodal/overview), select the "_Gemini 1.5 Pro"_ model, upload the PDF file and prompt:
```
Give me 5 thoughtful questions to ask to the presenter of the talk in the PDF file
```

<br/>

### Organize quizzes for the attendees
Sometimes there are gadgets and swags to distribute to event attendees. Instead of randomly assigning them with a raffle, why not rewarding who really listened to the content presented? Assuming there is a PDF of the session, there is an easy way to generate questions and answers.  
Use [Vertex AI Studio Multimodal](https://cloud.google.com/vertex-ai/generative-ai/docs/multimodal/overview), select the "_Gemini 1.5 Pro"_ model, upload the PDF file and prompt:
```
I want to organize a quiz based on the PDF file.
Give me 6 questions with multiple choices, and their answers
```

In case the content is suitable for a more "interactive" approach, the following prompt can be very inspirational:
```
Using the attached file, create 7 riddles, in rhymes, and their answers.
Each riddle starts with a statement, and finishes with a question
```


<br/>

## Event wrap-up

### Summarize the content of the session
If there is a **YouTube video of the session** available, [Google Gemini YouTube extension](https://support.google.com/gemini/answer/13695044) can help quickly summarize, analyze and ask questions about the video. Given video captions are available.

Open [Gemini app](https://gemini.google.com/) and try the following prompt:
```
Please summarize the content of the video at https://www.youtube.com/watch?v=9YowQrFxEWg using 6 bullet points
```

Too long? 
```
Make the previous answer shorter
```

The prompt works also with published, but unlisted, YouTube videos. 
<br/>

If **only audio is available**, it's possible to use [Vertex AI Studio Multimodal](https://cloud.google.com/vertex-ai/generative-ai/docs/multimodal/overview), select the "_Gemini 1.5 Pro"_ model, upload the audio file and prompt:
```
Summarize in 4 bullet points
```
With 1M context window (and counting), up to 11 hours of audio can be summarized.
<br/>

Similar approach if only **slides of the sessions** are available. Using Gemini 1.5 Pro model in Vertex AI Studio Multimodal it would be possible to summarize the PDF document of the session.

<br/>

### Prepare the wrap-up email
Open [Google Gemini app](https://gemini.google.com/) and try the following prompt, using the bullet points generated in the previous step:
```
The following bullet points were taken from a session presented at an event. Using them, prepare a wrap-up email to send to all the event attendees. Please also add a feedback request and ask them to register to the community to stay updated on upcoming events.

* Importance of MFA: Multi-factor authentication (MFA) is crucial for securing your Google accounts and preventing unauthorized access. It stops nearly all common account attacks.

* Setting up Google 2SV: Visit myaccount.google.com to enable and configure 2-Step Verification (2SV), Google's MFA solution.

* Recommended Factors: For optimal security, set up these four factors in order of priority: Security Key, Google Authenticator App, Device Push, and Backup Codes.

* Factor Comparison: The video discusses the various MFA factors, including their security levels and potential drawbacks. Security keys are the most secure, while text messages are less secure but still significantly better than no MFA.
```


<br/>

## Reporting and Analysis

### Count event attendees
Ideally, event attendees should be checked-in at the entrance. In case it wasn't possible, GenAI comes to the rescue. Take a photo of the event attendees (front audience or at the back of the room both work), use [Vertex AI Studio Multimodal](https://cloud.google.com/vertex-ai/generative-ai/docs/multimodal/overview), select the "_Gemini 1.0 Pro Vision"_ model, upload the image file and prompt:
```
How many people there are in the picture?
```
Enjoy an automatic count of the number of attendees.

<br/>

### Attendees Analysis

Steps
- Open Gemini
- TODO: get your answers from Bevy
- Ask it if it will summarize a set of data, giving as much specifics as possible (i.e. please summarize this survey data from an internal reading challenge). Paste the data and press enter.
  - One challenge I came across though was that sometimes Gemini would hallucinate and I had to try different prompts and ways to verify if how it categorises the responses is legit. Asking to illustrate data categorisation with quotes from respondents proved to work the best. 


<br/>

## Final consideration
- As usual, If you want Gemini to perform several related tasks, break them apart into separate prompts. This helps the AI understand the task and provide useful responses.
- Worried about the price for using Vertex AI?
  - [Details on the pricing model](https://cloud.google.com/vertex-ai/generative-ai/pricing)
  - The audio example will cost $0.06:  _$0.00265 / second * 4.5 mins * 60 seconds_


### Additional resources
- https://cloud.google.com/vertex-ai/generative-ai/docs/start/quickstarts/quickstart-multimodal?hl=en
- https://cloud.google.com/vertex-ai/generative-ai/docs/multimodal/overview


<br/>
<br/>

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

## TODO
### Ollama
https://github.com/ollama/ollama
https://ollama.com/  
brew iinstall --cask ollama
https://ollama.com/library, and insall gemma:7b (ollama run gemma:7b)
http://localhost:11434/

ollama pull gemma:2b
ollama pull nomic-embed-text
