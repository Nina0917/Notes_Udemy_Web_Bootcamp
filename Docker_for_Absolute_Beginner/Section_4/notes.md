## Docker Images

docker build . -f Dockerfile -t mmumshad/my-custom-app

- Build a docker image based on the Dockerfile, -f specifies the file name
- The build context is . (current directory)
- The -t flag is used to assign a tag or name to the built image (mmumshad/my-custom-app).

docker push mmumshad/my-custom-app

- Publish the image
- Mmumshad is the personal account and my-custom-app is name of the image

When Docker builds images, it builds these in a layered architecture.

All the layer builds are cashed by Docker.

If you add additional steps in the Dockerfile, it will reuse the previous layers from cache and continue to build the remaining layers.

## Demo - Creating a new Docker Image

How to deploy the application manually?

docker run -it ubuntu bash

- run a Docker container based on the Ubuntu image and start an interactive bash session within the container.
- ‘-t’ means terminal, ‘-i’ means standard input

apt-get update

- apt-get install -y python
- Apt-get is a command used in ubuntu
- ‘-y’ stands for ‘yes’

apt-get install python-pip

- pip install flask
- PIP is a package manager for Python packages. Note: If you have Python version 3.4 or later, PIP is included by default.

cat > /opt/app.py

- Copy the code and paste it into the file app.py within the folder opt

cd opt
FLASK_APP=app.py flask run –host=0.0.0.0

- **Enter the location of the file app.py**
- Start the web server

history

- Run history command and pull down all instructions

---

How to dockerize the application?

mkdir my-single-webapp
cd my-single-webapp
cat > Dockerfile

- FROM ubuntu
- RUN apt-get update
- RUN apt-get install -y python python-pip
- RUN pip install flask
- COPY app.py /opt/app.py
- ENTRYPOINT FLASK_APP=/opt/app.py flask run –host=0.0.0.0

cat > app.py

- Paste the application source code

docker build . -t my-simple-webapp

- Build image and gave it a tag

docker run my-simple-webapp

- Run the image we just build

---

How to push images?

docker build . -t mmumshad/my-simple-webapp

docker login

- Then input the username and pass

docker push mmumshad/my-simple-webapp

- Mmumshad is a personal account name, you have to tag your image with your account name to publish it.

## Environmental Variables

How to set environment variables?

docker run -e APP_COLOR=blue simple-webapp-color

- Set environment variable APP_COLOR to blue

<br>

How to check current container’s environment variable?

docker inspect blissful_hopper

- Use inspect

## Command vs Entrypoint

CMD command param1 = CMD[“command”, “param1”]

<br>

```
FROM Ubuntu
CMD sleep 5
```

docker run ubuntu-sleeper

- It will automatically sleep for 5 sec

```
FROM Ubuntu
ENTRYPOINT [“sleep”]
```

docker run ubuntu-sleeper 10

- In case of entry point, the command line parameters will get appended

```
FROM Ubuntu
ENTRYPOINT [“sleep”]
CMD[“5”]
```

docker run ubuntu-sleeper

- It sleeps 5 sec
  docker run ubuntu-sleeper 10
- It overrides CMD
