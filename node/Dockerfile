FROM node:15 AS builder

WORKDIR /usr/src/app

RUN apt-get update && apt-get install -y wget

ENV DOCKERIZE_VERSION v0.6.1
RUN wget https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && tar -C /usr/local/bin -xzvf dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && rm dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz

COPY ./package*.json /usr/src/app/

# RUN npm install

COPY . /usr/src/app

EXPOSE 3000

# CMD [ "node", "index.js" ]

# RUN npm init && \
#     npm install express --save && \
#     npm install mysql --save

# FROM node:alpine.3.15

# WORKDIR /usr/src/app

# COPY --from=builder /usr/src/app .

# RUN chown -R www-data:www-data /usr/src/app

# EXPOSE 3000