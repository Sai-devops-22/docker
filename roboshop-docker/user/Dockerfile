FROM node:alpine3.21 AS builder
WORKDIR /opt/server
COPY package.json .
COPY *.js .
RUN npm install

FROM node:alpine3.21
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
WORKDIR /opt/server
RUN chown -R roboshop:roboshop /opt/server
ENV MONGO = "true" \
    REDIS_URL = 'redis://redis:6379' \
    MONGO_URL = "mongodb://mongodb:27017/user"
USER roboshop
COPY --from=builder /opt/server /opt/server
CMD ["node","server.js"]



# FROM node:20
# WORKDIR /opt/server
# COPY package.json .
# COPY *.js .
# RUN npm install
# ENV MONGO = "true" \
#     REDIS_URL = 'redis://redis:6379' \
#     MONGO_URL = "mongodb://mongodb:27017/user"
# CMD ["node","server.js"]

