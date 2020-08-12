FROM node:alpine

#Set working directory
WORKDIR '/app'

#Set up packages
COPY ./package.json ./
RUN npm install

#Set up the client files
COPY . .

#Set default command
CMD ["npm","run","start"]
