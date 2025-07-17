ARG version
FROM almalinux:${version:-9}
ENV course="devops" \
    duration="120hrs"
ARG trainer="sivakumar"
ENV trainer=$trainer  
#to use the arg file in container
RUN echo "Hi, Course is: ${course}, duration is: ${duration}, trainer is: ${trainer}, version: ${version}"
CMD ["sleep", "1000"]