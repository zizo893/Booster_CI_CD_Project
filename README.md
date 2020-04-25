# Booster_CI_CD_Project

Create CI/CD pipeline using jenkinsfile to deploy simple django web app as a microservice running on docker container locally

# Steps

1- Fork this repo to your account

2- write dockerfile inside the forked repo to create new image from base image ubuntu and install python3.6 and pip3 and copy the source code files of the app to this image and configure it to start the server when creating container (check the below section for steps to start the django server) 

3- write jenkinsfile using scripting syntax with the following four stages

- preparation: checkout the code

- build image: build image using the dockerfile

- push image: push the built image to docker registry(docker hub)

- deploy: deploy a container from the pushed image


4- configure job in jenkins using pipeline type with the forked git repo url



# Steps to start django server


  install required packages:

      pip3 install -r requirements.txt

  make migrations for DB:

      python3.6 manage.py makemigrations

  apply the migrations:

      python3.6 manage.py migrate

  start the server:

      python3.6 manage.py runserver 0.0.0.0:8000
