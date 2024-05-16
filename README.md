# How GenAI can help community events planning, execution and analysis

Author: [Alfredo Morresi](https://rainbowbreeze.it)


As a community manager, are you tired of juggling event details and missing out on creative inspiration?  
Here some practical strategies to leverage GenAI-powered tools for community managers, and optimize the entire event planning, exectuion and reporting process. Tips to help with creative asset and marketing material creation, session topic selection, survey analysis, attendee data insights, and more.

Do you have your "magic tips" to share? Pull requests are welcome!


<br/>

## A word on prompting

Prompt engineering is an art. Practive it without fear of making mistakes!

### Some suggestions
1. Clearly communicate what **content or information is most important**. Focus on telling the model exactly what you want it to do, and refine iteratively telling it what not to do.
1. Defining the **role** if using one. For example, _You are an experienced UX designer at a tech company_, or _You are a senior community manager_, etc.
1. Include **context and input data**.
1. Use specific, varied **examples** to help the model narrow its focus and generate more accurate results.
1. Use **constraints** to limit the scope of the model's output. For example, Make sure to limit your response to 3 sentences.. This can help avoid meandering away from the instructions into factual inaccuracies.
1. Break down complex tasks into a **sequence** of simpler prompts.
1. Instruct the model to **evaluate or check** its own responses before producing them. Some examples are: _Rate your own work on a scale of 1-10_, or _Do you think this is correct? Why?_, etc.
1. When prompting the model to gather information or explain a topic, encourage it to cite its **source material**.
1. If one-shot prompting doesn't work, break apart the process in multiple steps, create a specialized **agent** to take care of each step, and chain the output of an agent as the input for the next one, to arrive to the desired results.

<br/>

### General considerations
- For the most part, Gemini and LLMs may be accurate, but they are prone to errors, so you might want to take the information with a pinch of salt.
- Human review is a large part of the LLM improvement process. Do not enter sensitive or personal information.
- And perhaps most important: Be creative! LLMs and prompt engineering are still in their infancy, and evolving every day. Who knows, you might even discover the newest emergent ability.

Suggestions on prompting? https://ai.google.dev/examples


<br/>

## What you need to know
In order to try the different suggestions, a way to access [Gemini mulltimodal](https://cloud.google.com/vertex-ai/generative-ai/docs/multimodal/overview) capabilities is required.
- [Google AI Studio](https://ai.google.dev/)
  - Free to use to test the different prompts
  - [List of available countries](https://ai.google.dev/gemini-api/docs/available-regions)
- [Vertex AI Studio Multimodal](https://cloud.google.com/generative-ai-studio)
  - Setup a GCP account and project
  - Open [Vertex AI Studio](https://console.cloud.google.com/vertex-ai/generative) homepage
    - Open "Multimodal Home"
    - Select "Prompt design (single turn)" or open one of the Sample prompts
- [Gemini app](https://gemini.google.com/)
  - Open [Gemini app](https://gemini.google.com/)
    - Free usage for the basic model
    - To use the Gemini Advanced model, a [Google One AI Premium plan](https://one.google.com/explore-plan/gemini-advanced) has to be activated (free for the first 2 months)
- Other options
  - [Vertex AI Studio CLI](https://cloud.google.com/vertex-ai/docs/start/cloud-environment)


<br/>

## Describe the community

### Create a compelling community landing page
The community landing page is an important showcase to "tell the why and the how" of the community, and attract new members. How to capture its true essence and put it into words? For example, using footage of past community experiences.

After gathering some pictures of past events, access Vertex AI Studio Multimodal, select the "_Gemini 1.5 Pro"_ model, upload the images and prompt:
```
You are a content writer and you want to write an engaging landing page text to present a community and its activities, based on the uploaded pictures.
The community name is GDG Rainbow.
It should talk about the importance of tech communities, providing examples of their activities taken from these pictures, and invite readers to join the community events to learn something new about Google technologies.
Put emphasis on the learning opportunities offered on Google technologies, and the possibility to create connections with the local ecosystem of developers.
``` 

Things to try:
- Different variation of the output can be obtained changing temperature parameter, specifying style of the text, etc.
- The more context you give to Gemini, the better it can understand your request and generate a useful response.
- [Gemini app](https://gemini.google.com/) can process only one picture at time. Vertex AI Studio, instead, can take more images as input.
- If there are no past pictures to show, what about using the ones from "twin communuties"?

<br/>


<br/>

## Organizing an event

### Generate event title and description
Once the topic of the session is decided, prompts can help generating session titles and descriptions to get inspired from. 

In Gemini app, prompt:
```
You're a community manager.
You organized a speaker session about how to build the first GenAI powered Android app, using Vertex AI.
Write a text to present the event to a potential audience, including the event agenda.
```

Let's add some event-specific context:
```
You're a community manager.
You organized a speaker session about how to build the first GenAI powered Android app, using Vertex AI.
Write a text to present the event to a potential audience, including the event agenda.
The event will be hosted in SkillsShare tech space in Pavia, on May 24 from 6:00 to 8:00pm.
Alfredo Morresi will be the speaker.
Focus on the unique aspects of the event: it's the first one in the Pavia area about this topic, the speaker is a well-known expert on Android app development, the Q&A session will give the audience an opportunity to ask about real-world experience in developing this kind of mobile app.
```

Now, let's create some social-media snippets:
```
You're a social media manager.
You need to write a text tailoed for X and LinkedIn social media to advertise a speaker session about how to build the first GenAI powered Android app, using Vertex AI.
List hashtags to use.
```

Too hyperbolic? Let's fix it:
```
You're a social media manager.
You need to write a text tailoer for X and LinkedIn social media to advertise a speaker session about how to build the first GenAI powered Android app, using Vertex AI.
List hashtags to use.
The post targets a tech audience, so avoid all the marketing buzz.
```

<br/>

### Improve accessibility with alt text
Images help people understand content and make it more pleasant, but for those with visual impairments, alt tags are crucial. They describe the image and provide context, making your community or event page accessible and SEO-friendly.  
To generate alt text for images:
- Open [Vertex AI Studio Vision](https://console.cloud.google.com/vertex-ai/generative/vision)
- Uploade the image and click on "Generate Caption"
- (_Adjust and_) Copy the generated text to add in the ALT attribute of the image


<br/>

## Before the event 

### Understand your event audience
Using community platforms which allow to gather RSVPs and ask for attendees questions, is possible to get insights on what they expect from the event, and potentially make adjustement to tailor-made the event for them.  

For example, [GDG Event Platforms](https://gdg.community.dev/) asks these additional questions during the event registration (more can be added by community organizers), and allows to export them as CSV for further analysis:
- How did you learn about this event? _[multiple choice]_
- My level of developer experience is... _[multiple choice]_
- What are you most excited to learn about at this event? _[free text]_

Using [this event](https://gdg.community.dev/events/details/google-google-developer-community-online-presents-build-conversational-ai-experiences-powered-by-llms/) as example, it's possible to export the RSVP data into a CSV, upload the file (_or drag and drop it_) in Vertex AI Studio Multimodal, select the "_Gemini 1.5 Pro"_ model, and prompt:
```
How did the attendees know about the event? Show percentage and detailed analysis
```
Or
```
What's the average experience of event attendees, and what they expect from the event?
```



<br/>

## At the event

### Generate question for the Q&A session with the speaker
It may happen that no one wants to break the ice during a Q&A session making the first question. Hence, having a list of few ready-made ones to fill that awkward silence can be helpful.  
If the speaker provides a presentation in advance, it's possible to get them using Vertex AI Studio Multimodal, select the "_Gemini 1.5 Pro"_ model, upload the PDF file and prompt:
```
Give me 5 thoughtful questions to ask to the presenter of the talk in the PDF file
```

<br/>

### Organize quizzes for the attendees
Sometimes there are gadgets and swags to distribute to event attendees. Instead of randomly assigning them with a raffle, why not rewarding who really listened to the content presented? Assuming there is a PDF of the session, there is an easy way to generate questions and answers.  
Use Vertex AI Studio Multimodal, select the "_Gemini 1.5 Pro"_ model, upload the PDF file and prompt:
```
I want to organize a quiz based on the PDF file.
Give me 6 questions with multiple choices, and their answers
```

In case the content is suitable for a more "interactive" approach, the following prompt can be very inspirational:
```
Using the attached presentation, create 7 riddles, in rhymes, and their answers.
Each riddle starts with a statement, and finishes with a question
Provide 3 alternative replies: one correct and two wrong.
Quote the slide the riddle refers to, and the correct reply.
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

If **only audio is available**, it's possible to use [Vertex AI Studio Multimodal](https://cloud.google.com/vertex-ai/generative-ai/docs/multimodal/overview), select the "_Gemini 1.5 Pro"_ model, upload the audio file (_drag and drop it the upload grays out the file_) and prompt:
```
Summarize in 4 bullet points
```
With 1M context window (and counting), up to 11 hours of audio can be summarized.  

Worried about the price for using Vertex AI? [Details on the pricing model](https://cloud.google.com/vertex-ai/generative-ai/pricing), and an audio example of 4 mins costs $0.06:  _$0.00265 / second * 4.5 mins * 60 seconds_

Similar approach if only **slides of the sessions** are available. Using Gemini 1.5 Pro model in Vertex AI Studio Multimodal it would be possible to summarize the PDF document of the session.

<br/>

### Prepare a wrap-up email
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

### Attendees feedback analysis
Similarly to the attendees RSVP replies, it's possible to analyze the attendees feedback, assuming they replied to the attendees feedback forms. GDG Event Platform ask for these questions:
- Would you join another event organized by this community based on your experience? _[multiple choice]_
- How well did the content of the event meet your expectations?_[multiple choice]_
-	What topic did you like most at this event?_[free text]_
-	Do you plan to implement what you learned in the near future?_[multiple choice]_
-	I felt included at this event _[multiple choice]_

After exporting the replies in a CSV for this [example event](https://gdg.community.dev/events/details/google-google-developer-community-online-presents-build-conversational-ai-experiences-powered-by-llms/), upload the file (_or drag and drop it_) in Vertex AI Studio Multimodal, select the "_Gemini 1.5 Pro"_ model, and prompt:
```
Analyze attendees satisfaction score and groups topics they liked the most
```

Or something sligtlhy more advanced:
```
How the willingness to suggest the event and satisfaction score are correlated?
```

Please note: LLMs sometimes allucinate: try different and specific prompts and verify them. Asking to illustrate data categorisation with quotes from respondents proved to work the best. 


<br/>

## Conclusion
GenAI can help a lot in the entire event organization flow. As usual, creativity in prompting, iterations and adding specif context and commands will produce the best results.
There are other tasks, not yet included in this presentation, where LLM could help. For example:
- Create opening notes for the event
- Generate creativity for the event
- Generate a wrap-up blogpost about the event (using slides of the content, picture of the attendees)
- Write a detailed description of the session to upload to YouTube

Have a great event planning!


<br/>
<br/>
<br/>
<br/>

## IGNORE - Ideas to explore
Sources for event topics
- https://github.com/trending
- https://dev.events/
- https://www.gdeltproject.org/about.html

Sources for conferences and speakers
- https://www.wearedevelopers.com/
- https://ng-conf.org/speakers/
- https://nyc24.devrelcon.dev/
- https://conferences.codemotion.com/milan2023-live/agenda/

Image generation
- https://huggingface.co/spaces/stabilityai/stable-diffusion
- Deploy stablediffusion via VertexAI (also Imagen)
- HuggingFace checkpoint to call for getting images
- Deploy solution to HF so people can visit it

Find the right role
- You're an head hunter. You need to suggest the best role to contact companies to get sponsorships. What it will be, and why?


<br/>

## Speaker scouting
Scrapers
- https://github.com/VinciGit00/Scrapegraph-ai

Ollama  
- https://github.com/ollama/ollama
- https://ollama.com/  

```
brew install --cask ollama
https://ollama.com/library, and insall gemma:7b (ollama run gemma:7b)
http://localhost:11434/

ollama pull gemma:2b
ollama pull nomic-embed-text
```
