#use the official nodejs image for build the react app
FROM node:22.1.0 AS build

#set the working directory
WORKDIR /app

#copy the package.json and install dependencies
COPY package.json ./
RUN npm install

#copy the rest of the app code
COPY . .

#build the react app
RUN npm run build

#serve the app with nginx
FROM nginx:alpine

#copy the build folder to the nginx public folder
COPY --from=build /app/dist /usr/share/nginx/html

EXPOSE 80
