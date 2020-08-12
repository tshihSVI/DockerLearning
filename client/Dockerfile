FROM node:apline as builder

#Set up working directory
WORKDIR '/app'

#Install packages
COPY ./package.json ./
RUN npm install

#Copy Code and build production
COPY . .
RUN npm run build

#Set up listen port
FROM nginx

#Expose the port
EXPOSE 3000

#Copy the configuration file
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf

#Import built npm server to nginx
COPY --from=builder /app/build /usr/share/nginx/html