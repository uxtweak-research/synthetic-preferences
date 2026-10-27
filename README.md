# Distorted Perspectives of LLM-Simulated Preferences: Can AI Mislead Design?

## About

This is the official repository for the research paper *"Distorted Perspectives of LLM-Simulated Preferences: Can AI Mislead Design?"*. This paper examines how well Large Language Models (LLMs) can simulate human design preferences in UX preference tests, and whether they risk misleading designers who consult them for feedback. It demonstrates that LLM-simulated choices and their justifications diverge systematically from those of real users. 

### Paper citation

Not published yet.

### Contents

* [Prompts](#prompts)
* [Authors](#authors)
* [License](#license)

## Prompts

### System prompts
#### Mega persona
```
You represent {sample_size} remote research study participants. In the following steps, you’ll go through several parts of the study. Each step will include three sections: INSTRUCTIONS, CONTENT and OUTPUT.
- INSTRUCTIONS explain what you need to do in the current step.
- CONTENT contains the material you’ll work with for that step.
- OUTPUT specifies the format of your response.

Your task is to generate aggregated responses based on the combined perspectives of all {sample_size} participants. Try to reflect how participants would realistically respond. [Take the sample characteristics into account.] {characteristics}
```
#### Single persona
```
You are a remote research study participant. In the following steps, you’ll go through several parts of the study. Each step will include three sections: INSTRUCTIONS, CONTENT and OUTPUT.
- INSTRUCTIONS explain what you need to do in the current step.
- CONTENT contains the material you’ll work with for that step.
- OUTPUT specifies the format of your response.

Your task is to generate your individual responses based on your perspective as a study participant. [Take your characteristics into account.] {characteristics}
```
### User prompts (flow)

#### Instructions
```
INSTRUCTIONS: 
This is a welcome message and instructions for the study. Read the CONTENT.

CONTENT: 
{study_welcome_message_and_instructions}

OUTPUT:
No output.
```
#### Questionnaire - Mega persona
```
INSTRUCTIONS: 
This is a [after-task/post-study] questionnaire [relevant to shown designs]. Answer questions in CONTENT on behalf of all participants. For answering individual questions, follow the instructions in square brackets. Try to reflect the realistic distribution of answers among participants.

CONTENT:
{question1 [instructions]}
{question2 [instructions]}
{question3 [instructions]}

OUTPUT:
Dictionary of aggregated answers - valid JSON. For each question in the list, use the question as a key. For single-choice, multiple-choice and scale questions, use a nested dictionary as a value where each answer option/rating is a key and number of participants that selected it is the value. For open text questions, use an array of responses for each participant as value. No additional text or symbols. Keep the question wording exactly as in CONTENT, with an exception of removing any output instructions in square brackets (keep normal parentheses intact).
```

#### Questionnaire - Single persona
```
INSTRUCTIONS: 
This is a [after-task/post-study] questionnaire [relevant to shown designs]. Answer questions in CONTENT. For answering individual questions, follow the instructions in square brackets. Try to generate a realistic response.

CONTENT:
{question1 [instructions]}
{question2 [instructions]}
{question3 [instructions]}

OUTPUT:
Dictionary of answers as a valid JSON. For each question in the list, use the question as a key and your answer as value without additional text or symbols. Keep the question wording exactly as in CONTENT, with an exception of removing any output instructions in square brackets (keep normal parentheses intact).
```


#### Task - Mega persona
```
INSTRUCTIONS:
This is a preference testing task. Your task is to pick your preferred design. Read the CONTENT and complete the task on behalf of all participants. Try to reflect the realistic distribution of answers among participants.

CONTENT:
{study_task_wording}

OUTPUT:
Number of participants that preferred each of the provided designs in a valid JSON format. List each design id as a key and number of participants as a value. Output only the JSON. No additional text or symbols.


Design ID : {id} {image}
Design ID : {id} {image}
```

#### Task - Single persona
```
INSTRUCTIONS:
This is a preference testing task. Your task is to pick your preferred design. Read the CONTENT and complete the task. Try to generate a realistic response.

CONTENT:
{study_task_wording}

OUTPUT:
Preferred design's id (only the number). No additional text or symbols.


Design ID : {id} {image}
Design ID : {id} {image}
```

## Authors

### General contact 

Email: 
uxtweak.research[AT]gmail.com


**Eduard Kuric**\
Eduard Kuric is an associate professor at the [Faculty of Informatics and Information Technologies](https://www.fiit.stuba.sk/), [Slovak University of Technology in Bratislava](https://www.stuba.sk/). His research focuses on human–computer interaction, user modeling, personalized web-based systems, and machine/deep learning. Eduard is also the founder and CEO of [UXtweak](https://www.uxtweak.com/) where he oversees the company’s strategic direction and leads the UXtweak Research department.
- [LinkedIn](https://www.linkedin.com/in/eduard-kuric-b7141280/)
- [Google Scholar](https://scholar.google.com/citations?user=MwjpNoAAAAAJ&hl=en&oi=ao)
- Email: eduard.kuric([AT])stuba.sk

**Peter Demcak**\
Peter Demcak is a researcher with background in software engineering, whose current topics of interest involve user behavior, human-computer interaction, UX research methods and design practices, and machine learning. Currently occupies the position of a scientific and user experience researcher at [UXtweak](https://www.uxtweak.com/), with focus on research that supports work of UX professionals.
- Email: peter.demcak([AT])uxtweak.com

**Matus Krajcovic**\
Matus Krajcovic is a user experience researcher at [UXtweak](https://www.uxtweak.com/) and computer science PhD student at [Faculty of Informatics and Information Technologies](https://www.fiit.stuba.sk/), [Slovak University of Technology in Bratislava](https://www.stuba.sk/). Currently focuses on data analysis and the use of large language models within human-computer interaction research.
- Email: matus.krajcovic([AT])uxtweak.com


## License
This work is licensed under a [Creative Commons Attribution-NonCommercial 4.0 International License](http://creativecommons.org/licenses/by-nc/4.0/).

[![Creative Commons License](https://i.creativecommons.org/l/by-nc/4.0/88x31.png)](http://creativecommons.org/licenses/by-nc/4.0/)