#use the official node.js image
FROM node:22.1.0

#Set the working directory in the container
WORKDIR /usr/src/app

COPY package.json ./
RUN npm install

COPY . .

#Expose the backend port
EXPOSE 5000

#Command to run the backend
CMD ["npm", "start"]