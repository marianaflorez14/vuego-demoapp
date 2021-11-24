# Frontend container

# Bring the oficial latest node image 
FROM node:14-alpine

# Establish the directory inside the container
WORKDIR /usr/src/app

#All package json are going to be copy in the first directory
COPY package*.json ./

# Copy project files and folders to the current working directory 
COPY . .

# Endpoint of the frontend
RUN echo "VUE_APP_API_ENDPOINT=\"http://localhost:4000/api\"" > .env.production

# install app dependencies

RUN yarn 

# build app for production with minification
RUN yarn build

# To install NGINX and execute the website on it
FROM nginx:alpine
COPY --from=0 usr/src/app/dist /usr/share/nginx/html

# Exposing 80 port for incoming requests
EXPOSE 80

