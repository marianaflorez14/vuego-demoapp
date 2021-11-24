# Backend image
# Bring the already created image by go
FROM golang:1.16-alpine3.13

# Establish the directory inside the container
WORKDIR /go/src/app

#
COPY . .

# Exposing PORT 4001 for the incoming requests
EXPOSE 4001 
ENV PORT=4001

# Building the project (because it is a go project)
RUN go build 

# When docker is running this will be executed 
CMD [ "./vuego-demoapp" ]