FROM almalinux:9
RUN dnf install nginx   -y
RUN mkdir /tmp/work-dir\
RUN cd /tmp/work-dir
RUN pwd
RUN echo "hello" > hello.txt

CMD ["sleep","1000"]