FROM python:3.7.9-stretch

RUN apt-get update && apt-get install -y \
    software-properties-common \
    apache2 \
    curl \
    python3-pip

#Install pip
RUN pip install --upgrade pip

#Defines the work environment inside our Docker image
WORKDIR /home/bot

#Copies requirements.txt to the image environment
COPY ./requirements.txt /home/bot/requirements.txt

#Installs the needed modules
RUN pip3 install -r requirements.txt

#Copies the Python script to the image environment
COPY ./bot-docker.py /home/bot/bot.py

#Executes the Python script
CMD [ "/bin/bash","-c","python3 /home/bot/bot.py" ]