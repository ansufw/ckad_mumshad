# Practice

## Questions
1. How many images are available on this host?
2. What is the size of the ubuntu image?
3. We just pulled a new image. What is the tag on the newly pulled NGINX image?
4. We just downloaded the code of an application. What is the base image used in the Dockerfile?
5. To what location within the container is the application code copied to during a Docker build?
6. When a container is created using the image built with this Dockerfile, what is the command used to `RUN` the application inside it.
7. What port is the web application run within the container?
8. Build a docker image using the Dockerfile and name it webapp-color. No tag to be specified.
9. Run an instance of the image webapp-color and publish port 8080 on the container to 8282 on the host.
10. Access the application by clicking on the tab named HOST:8282 above your terminal.
11. What is the base Operating System used by the python:3.6 image? If required, run an instance of the image to figure it out.
12. size image?
13. -
14. Build a new smaller docker image by modifying the same Dockerfile and name it webapp-color and tag it lite. Hint: Find a smaller base image for python:3.6. Make sure the final image is less than 150MB.
15. Run an instance of the new image webapp-color:lite and publish port 8080 on the container to 8383 on the host.

### Dockerfile webapp-color
```
FROM python:3.6
  
RUN pip install flask

COPY . /opt/

EXPOSE 8080

WORKDIR /opt

ENTRYPOINT ["python", "app.py"]
```

### Dockerfile webapp-color compress
```
FROM python:3.8.20-alpine3.19
  
RUN pip install flask

COPY . /opt/

EXPOSE 8080

WORKDIR /opt

ENTRYPOINT ["python", "app.py"]
```

## Answer
1. run `docker image ls`
2. see above
3. see tag on the result `docker image ls`
4. Inspect the Dockerfile in the webapp-color directory i.e. `cat Dockerfile`
5. see above
6. see above
7. see above
8. run `docker build -t webapp-color .`
9. run `docker run -p 8282:8080 webapp-color`
10. -
11. create instance from image python:3.6, run `docker run -it python:3.6 /bin/bash` and `cat /etc/os-release`
12. see on `docker image ls`
13. -
14. use alpine base image
15. run `docker run -p 8383:8080 webapp-color:lite`

