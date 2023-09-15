# Docker

## Commands

```
sudo service docker start

docker images
docker containers
```

## Docker Compose

```
docker-compose --version
```

## Getting Started

```
docker run -d -p 80:80 docker/getting-started
# or
docker run -dp 80:80 docker/getting-started
```

Return

```
Unable to find image 'docker/getting-started:latest' locally
latest: Pulling from docker/getting-started
59bf1c3509f3: Pull complete
8d6ba530f648: Pull complete
5288d7ad7a7f: Pull complete
39e51c61c033: Pull complete
ee6f71c6f4a8: Pull complete
f2303c6c8865: Pull complete
0645fddcff40: Pull complete
d05ee95f5d2f: Pull complete
Digest: sha256:aa945bdff163395d3293834697fa91fd4c725f47093ec499f27bc032dc1bdd16
Status: Downloaded newer image for docker/getting-started:latest
8d92f3f5dc56c598e89da9bf3e6292255b5376fe3bbf029d6bacecdfbd128dd5
```

- -d - run the container in detached mode (in the background)
- -p 80:80 - map port 80 of the host to port 80 in the container
- docker/getting-started - the image to use

http://localhost/tutorial/

## Our Application

### Getting our App

http://localhost/assets/app.zip

### Building the App's Container Image

Create a file named Dockerfile in the same folder as the file package.json with the following contents.

http://localhost:3000

```
FROM node:12-alpine
# Adding build tools to make yarn install work on Apple silicon / arm64 machines
RUN apk add --no-cache python2 g++ make
WORKDIR /app
COPY . .
RUN yarn install --production
CMD ["node", "src/index.js"]
```

Please check that the file Dockerfile has no file extension like .txt. Some editors may append this file extension automatically and this would result in an error in the next step.

If you haven't already done so, open a terminal and go to the app directory with the Dockerfile. Now build the container image using the docker build command.

```shell
docker build -t getting-started .
```

Return

```shell
[+] Building 16.2s (11/11) FINISHED
 => [internal] load build definition from Dockerfile                       0.1s
 => => transferring dockerfile: 266B                                       0.0s
 => [internal] load .dockerignore                                          0.0s
 => => transferring context: 2B                                            0.0s
 => [internal] load metadata for docker.io/library/node:12-alpine          1.7s
 => [auth] library/node:pull token for registry-1.docker.io                0.0s
 => [1/5] FROM docker.io/library/node:12-alpine@sha256:22c475fa74096d7d89  4.7s
 => => resolve docker.io/library/node:12-alpine@sha256:22c475fa74096d7d89  0.0s
 => => sha256:c049a5e21a30943490f08abfe02330c3345418b734b 6.54kB / 6.54kB  0.0s
 => => sha256:3d243047344378e9b7136d552d48feb7ea8b6fe14ce 2.81MB / 2.81MB  0.5s
 => => sha256:77097efd96d4f2387f397f269d3c962aded25c487 24.91MB / 24.91MB  2.7s
 => => sha256:fca9e648b17d49a2c85f76b6a9a0ba148873adc4676 2.36MB / 2.36MB  0.8s
 => => sha256:22c475fa74096d7d898d719c19ef064f1244cab7f30 1.43kB / 1.43kB  0.0s
 => => sha256:0b360a97161e2f33023e57692a7afe2b6b66b5c2675 1.16kB / 1.16kB  0.0s
 => => extracting sha256:3d243047344378e9b7136d552d48feb7ea8b6fe14ce0990e  0.2s
 => => sha256:76bc0f9d5fc60a107bb75725e4773ddede004a85d8bcd9b 448B / 448B  0.8s
 => => extracting sha256:77097efd96d4f2387f397f269d3c962aded25c487bc0d64e  1.5s

 => => extracting sha256:fca9e648b17d49a2c85f76b6a9a0ba148873adc46767a441  0.1s
 => => extracting sha256:76bc0f9d5fc60a107bb75725e4773ddede004a85d8bcd9bf  0.0s
 => [internal] load build context                                          0.1s
 => => transferring context: 4.61MB                                        0.1s
 => [2/5] RUN apk add --no-cache python2 g++ make                          7.6s
 => [3/5] WORKDIR /app                                                     0.0s
 => [4/5] COPY . .                                                         0.1s
 => [5/5] RUN yarn install --production                                    0.7s
 => exporting to image                                                     1.2s
 => => exporting layers                                                    1.2s
 => => writing image sha256:ebf4478bfded103555fdf5b5969d2bb0e95f93a876712  0.0s
 => => naming to docker.io/library/getting-started                         0.0s

Use 'docker scan' to run Snyk tests against images to find vulnerabilities and learn how to fix them

# second install

[+] Building 17.1s (11/11) FINISHED
 => [internal] load build definition from Dockerfile                       0.0s
 => => transferring dockerfile: 32B                                        0.0s
 => [internal] load .dockerignore                                          0.0s
 => => transferring context: 2B                                            0.0s
 => [internal] load metadata for docker.io/library/node:12-alpine          1.1s
 => [auth] library/node:pull token for registry-1.docker.io                0.0s
 => [1/5] FROM docker.io/library/node:12-alpine@sha256:22c475fa74096d7d89  0.0s
 => [internal] load build context                                          0.1s
 => => transferring context: 4.61MB                                        0.0s
 => CACHED [2/5] RUN apk add --no-cache python2 g++ make                   0.0s
 => CACHED [3/5] WORKDIR /app                                              0.0s
 => [4/5] COPY . .                                                         0.1s
 => [5/5] RUN yarn install --production                                   14.2s
 => exporting to image                                                     1.5s
 => => exporting layers                                                    1.5s
 => => writing image sha256:f9a213c042fb92e23f0c15d09f686fb8a04c9a735157e  0.0s
 => => naming to docker.io/library/getting-started                         0.0s

Use 'docker scan' to run Snyk tests against images to find vulnerabilities and learn how to fix them
```

### Starting an App Container

Now that we have an image, let's run the application!

```shell
docker run -dp 3000:3000 getting-started
```

open your web browser to http://localhost:3000

### Removing a container using the CLI

Get the ID of the container by using the docker ps command.

```
docker ps
```

Use the `docker stop` command to stop the container.

```
# Swap out <the-container-id> with the ID from docker ps
docker stop <the-container-id>
```

Once the container has stopped, you can remove it by using the docker rm command.

```
docker rm <the-container-id>
```

Starting our updated app container

```
docker run -dp 3000:3000 getting-started
```

$ docker push docker/getting-started
The push refers to repository [docker.io/docker/getting-started]
An image does not exist locally with the tag: docker/getting-started

docker tag getting-started YOUR-USER-NAME/getting-started
docker tag getting-started fabricegeib/getting-started

docker tag getting-started fabricegeib/getting-started

docker login -u fabricegeib

Login Succeeded

Logging in with your password grants your terminal complete access to your account.
For better security, log in with a limited-privilege personal access token. Learn more at https://docs.docker.com/go/access-tokens/

docker push YOUR-USER-NAME/getting-started
docker push fabricegeib/getting-started
