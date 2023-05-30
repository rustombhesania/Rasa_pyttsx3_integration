# Rasa_pyttsx3_integration
Here we integrate Rasa open source with pyttsx3 for Text to Speech in the chat bot

Steps to use this 
1. Do not clone this git repo !!! it will cause errors
2. create a new python env (i use conda python==3.9)
3. ``` pip install -r r.txt ``` in the new env
4. it Will install rasa and pyttsx3
5. run ``` pip show rasa ``` And ``` pip show pyttsx3``` to conform the work versions
6.  if rasa gives error [https://rasa.com/docs/rasa/installation/environment-set-up]
7. if pyttsx3 gives error in linux use this ``` conda install -c conda-forge gcc=12.1.0``` resolved in my case

## To run a demo
make a new folder and run ``` rasa init ``` in the folder -> This will create A mood-chat_bot
Rasa files will get created

Make changes in Rasa files as shown
### in actions/
in ``` actions.py```
Add the custom action as shown in the file

### in data/

- ``` nlu.yml```
Add intent "greet" in our case which is already present in default mood_bot

- ``` rules.yml ```
Add a rule as shown in the file which corresponds to a intent 

- ``` stories.yml ```
Add or replace lines as per needed, we are replacing it here

### in /

- ``` domain.yml ```
Add intents.
Add/create entitis not required in this demo.
Add actions As shown the in the file.

- ``` endpoints.yml ```
uncomment where it says 
```
action_endpoint:
 url: "http://localhost:5055/webhook"
 ```
# To Excute the Chat bot
Open Two terminals with the env active

Run ``` rasa run actions``` in first terminal. 
Run ``` rasa shell ``` in second terminal

Refer this to understand how custom actions work [https://www.youtube.com/watch?v=VcbfcsjBBIg]

