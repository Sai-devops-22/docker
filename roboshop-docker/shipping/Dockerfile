# FROM maven
# WORKDIR /opt/server
# COPY pom.xml .
# COPY src /opt/server
# RUN mvn clean package 
# RUN mv target/shipping-1.0.jar /opt/server
# ENV CART_ENDPOINT=cart:8080
#     DB_HOST=mysql
# CMD ["java","-jar","shipping.jar"]


#optimization
FROM maven AS builder
WORKDIR /opt/server
COPY pom.xml .
COPY src /opt/server

FROM maven
RUN adduser -S roboshop && addgroup -S roboshop -G roboshop 
WORKDIR /opt/server
RUN chown -R roboshop:roboshop /opt/server
RUN mv target/shipping-1.0.jar /opt/server 
ENV CART_ENDPOINT=cart \
    DB_HOST=mysql
EXPOSE  8080
USER roboshop
COPY --from=builder /opt/server /opt/server
CMD ["java","-jar","shipping.jar"]


# FROM maven
# WORKDIR /opt/server
# COPY pom.xml .
# COPY src /opt/server/src
# RUN mvn clean package 
# RUN mv /opt/server/target/shipping-1.0.jar /opt/server/shipping.jar 
# ENV CART_ENDPOINT=cart:8080 \
#     DB_HOST=mysql
# CMD ["java","-jar","shipping.jar"]
