FROM almalinux:9
RUN mkdir /tmp/workdir-demo
#RUN cd /tmp/workdir-demo #this cd will not work here so we use WORKDIR
WORKDIR /tmp/workdir-demo
RUN pwd
RUN echo "HELLO" > hello.txt
CMD ["sleep","1000"]