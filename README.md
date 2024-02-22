# Pro-Diction

# ⛳️ Target UN SDGs
<img src="https://raw.githubusercontent.com/suucong/Github-User-Content/main/sdg4.png" width=200/> <img src="https://raw.githubusercontent.com/suucong/Github-User-Content/main/sdg10.png" width=200/>

# ⛳️ Our Solutions
Hearing impaired often face difficulties in communicating effectively with non-disabled individuals, leading to discrimination in various aspects of society such as education and employment.

### 🚀 Future Fluent Communication
Hearing impaired learn pronunciation to ultimately communicate seamlessly with non-disabled individuals without relying on anyone else's assistance.

### 🚀 Current Fluent Communication:
Even without pronunciation training and correction, real-time communication with non-disabled individuals is facilitated through sign language or text.

# 📱 How to use
<img src="https://raw.githubusercontent.com/suucong/Github-User-Content/main/splash&login.gif"/>
<img src="https://raw.githubusercontent.com/suucong/Github-User-Content/main/onboarding.gif"/>
<img src="https://raw.githubusercontent.com/suucong/Github-User-Content/main/mypage.gif"/>

# 🛠️ Project Architecture
<img src="https://raw.githubusercontent.com/suucong/Github-User-Content/main/TechStack.png"/>

## Backend
### 1. Tech Stack
- Java 17
- Springboot, Spring Security
- Spring Data JPA
- MySQL
- Redis
- Docker, Docker-compose
- GCP Compute Engine

### 2. Architecture
- I built a Docker image for our Spring Boot project using a Dockerfile and pushed it to Dockerhub.
- Next, I used the Vim text editor within a GCP Compute Engine instance to write the docker-compose.yml file.
- After that, I pulled the Spring Boot image, along with MySQL and Redis images. 
- Running 'docker-compose up -d' created the necessary containers. 
- Subsequently, I utilized a Docker MySQL container to create a user, schema, and database. 
- Backend communicated with the frontend using the server container we created. 
- To connect to an external API for pronunciation testing, the frontend sent recorded audio files to the server using Multipart. 
- The server then handled the encoding to Base64 and sent the encoded values to the external API. 
- Additionally, we stored Refresh Tokens in the Redis container for user authentication and authorization.
- The external API processed the audio, returned the pronunciation scores to the server, which in turn forwarded them to the frontend.
- Furthermore, to play pronunciation practice videos, the backend sends the string that needs to be pronounced to an AI server. The AI server then separates the consonants and vowels in the string.

### 3. ERD
<img src="https://raw.githubusercontent.com/suucong/Github-User-Content/main/erd2.png"/>

## Frontend
### 1. Tech Stack
- Kotlin plugin version 1.9.0

### 2. Architecture
- Google's TextToSpeech (TTS) built into Android was used to read sign language by voice or play text by voice. In addition, using a SpeechRecognizer (STT), it was possible to return the other person's voice as text.
It was implemented to recognize sign language through a camera on Android devices using MediaPipe's Hand Gesture Recognition.

## AI
### 1. Tech Stack
- ffmpeg 6.1.1
- fastapi 0.109.0
- uvicorn 0.26.0
- gunicorn 21.2.0
- python-multipart 0.0.6
- audiosegment 0.23.0
- google-cloud-speech 2.23.0
- pydub 0.25.1
- librosa 0.10.1
- soundfile 0.12.1

### 2. Architecture
- We used MediaPipe's Gesture Recognizer to train sign language recognition model 
- Using the audiosegment, pydub, librosa, ffmpeg, and google-cloud-speech libraries, we implemented a syllable-by-syllable breakdown of a single voice file by separating it into chunks of more than a certain number of waves, and then using Google's speech to text technology to recognize the pronunciation of each syllables

# Member
|Member|[이서현 (Lee Seohyun)](https://github.com/bimeon)|[노수진 (Sujin Roh)](https://github.com/suucong)|[김하연 (Kim Hayeon)](https://github.com/hyhy0623)|[김예솔 (Kim Yesol)](https://github.com/yesolthee)|
|:--:|:--:|:--:|:--:|:--:|
|Role|PM / AI Developer|Backend Developer|Frontend Developer|UX-UI Designer|
|Profile|<img src="https://raw.githubusercontent.com/suucong/Github-User-Content/main/sh.png" width="100" height="100"/>|<img src="https://raw.githubusercontent.com/suucong/Github-User-Content/main/sujin.jpg" width="100" height="100"/>|<img src="https://raw.githubusercontent.com/suucong/Github-User-Content/main/hy.png" width="100" height="100"/>|<img src="https://raw.githubusercontent.com/suucong/Github-User-Content/main/yesol.jpg" width="100" height="100">|
