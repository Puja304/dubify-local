# Dubify
DUBIFY VERSION 1.0.0 

DESCRIPTION
While it is fairly simple to be able to find instant AI generated subtitles for any video, it is without a doubt more benficial to have an auditory translation in the language one is comfortable in. Motivated by this idea, i decided to try and build a platform that does exactly this. 

OVERVIEW:

I use a simple python backend that takes in a video and generates a timestamped transcript for it. For each sentence in the transcript, I ask a model to try and translated it into the target languages, and make my tts model speak it. If the translation is significantly shorter or longer than the original when spoken, I ask for some paraphrtasing. Failing 5 attempts at that, I mess with the speaking speed a little to have each sentence spoken in roughly the same time. I then stitch the sentence audios together based on the start times of the original sentencesx (silence in between). Lastly, I strip the original video of audio and add the new audio, finsihing the dubbing.

FRAMEWORK:
React.js frontend and Flask backend 

COMMANDS:
    
  This is the local version of my project, to find the deployed version, refer to : https://github.com/Puja304/video-dubber
  To run this, clone the repository locally

  Then:
    1. Generate a free key at https://openrouter.ai/ and copy it
    1. Go to flask-server/prompt-responder.py and insert your new key in line 5: api_key="YOUR_API_KEY"
    1. cd flask-server && python -m venv venv && pip install -r requirements.txt && python app.py
    2. cd .. (back to root)
    3. cd frontend && npm install && npm start

RESULTS:
I have been successful in adding features that allow for video uplaods, preview of the dubbing, and an option to download the dubbed video. If not inclined to wanting to clone and run the 
other repo locally, please refer to the following for a test run: https://drive.google.com/file/d/1WzddGlrzBKZBNOrk_roEP5sYDV1VnY5g/view?usp=sharing

FUTURE GOALS:
There are a number of things I would like to imporove on in the future:
    1. Preserve background music and only replace the speech
    2. Increase support for lamguages
    3. Add more naturalized tts (make it sound less robotic)

