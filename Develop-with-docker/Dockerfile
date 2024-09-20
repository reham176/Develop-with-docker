FROM node:13-alpine

ENV MONGO_DB_USERNAME=admin \
    MONGO_DB_PWD=password
ARG DEFAULT_PORT=3000
#2a2dr to pass this arg wana build image
ENV PORT $DEFAULT_PORT 
#laken pass this env wana b run el image             
#3000
RUN mkdir -p /home/app

WORKDIR /home/app

COPY ./app/package.json .
RUN npm install

COPY ./app /home/app

# set default dir so that next commands executes in /home/app dir
#WORKDIR /home/app

# will execute npm install in /home/app because of WORKDIR
#RUN /home/app


EXPOSE 3000

# no need for /home/app/server.js because of WORKDIR
CMD ["node", "server.js"]
