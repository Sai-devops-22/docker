FROM node:20-alpine3.21 AS builder
WORKDIR /opt/server
COPY package.json .
COPY *.js .
RUN npm install

FROM node:20-alpine3.21
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
ENV MONGO="true" \
    MONGO_URL="mongodb://mongodb:27017/catalogue"
WORKDIR /opt/server
USER roboshop
COPY --from=builder /opt/server /opt/server
CMD ["node","server.js"]
# FROM node:alpine3.21
# RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
# WORKDIR /opt/server
# COPY package.json .
# COPY *.js .
# RUN npm install
# RUN chown -R roboshop:roboshop /opt/server
# ENV MONGO = "true" \
#     MONGO_URL="mongodb://mongodb:27017/catalogue"
# USER roboshop
# CMD ["node","server.js"]


#explanation
#first take software that has less size
#add group and user
#RUN addgroup -S roboshop && adduser -S roboshop -G roboshop

#change ownership user:group /file/
#RUN chown -R roboshop:roboshop /opt/server

#create working dicr
#WORKDIR /opt/server


#create USER roboshop


#copy the file path from previous build and paste it cureent workdir
#COPY --from=builder /opt/server /opt/server