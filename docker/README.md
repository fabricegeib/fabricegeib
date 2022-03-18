# Docker

## Getting Started

```
docker run -d -p 80:80 docker/getting-started
# or
docker run -dp 80:80 docker/getting-started
```

- -d - run the container in detached mode (in the background)
- -p 80:80 - map port 80 of the host to port 80 in the container
- docker/getting-started - the image to use

http://localhost/tutorial/

## Our Application

Create a file named Dockerfile in the same folder as the file package.json with the following contents.


FROM node:12-alpine
# Adding build tools to make yarn install work on Apple silicon / arm64 machines
RUN apk add --no-cache python2 g++ make
WORKDIR /app
COPY . .
RUN yarn install --production
CMD ["node", "src/index.js"]
Please check that the file Dockerfile has no file extension like .txt. Some editors may append this file extension automatically and this would result in an error in the next step.