## Docker Compose

Firtst, let’s use docker run command to run containers

docker run -d - -name=redis redis

docker run -d - -name=db postgres

docker run -d - -name=vote -p 5000:80 voting-app

docker run -d - -name=result -p 5001:80 result-app

docker run -d - -name=worker worker

<br>

In order to make the voting-app aware of the Redis service:

docker run -d - -name=vote -p 5000:80 - -link redis:redis voting-app

- The first ‘redis’ is the redis container’s name
- In source code of voting-app, it’s looking for the ‘redis’ host. So the second ‘redis’ is the name of host the voting-app is looking for.

Similar to result-app:

docker run -d - -name=result -p 5001:80 - -link db:db result-app

<br>

Finally, the worker application requires access to both
