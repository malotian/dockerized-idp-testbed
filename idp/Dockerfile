FROM maven:3.6.3-jdk-11
RUN git clone https://github.com/malotian/malotian.shibboleth.release.attributes.post.processor.git malotian.shibboleth.release.attributes.post.processor
RUN mvn -f malotian.shibboleth.release.attributes.post.processor/pom.xml package -Dmaven.test.skip=true
RUN unzip /malotian.shibboleth.release.attributes.post.processor/target/com.malotian.shibboleth.release.attributes.post.processor-0.0.1-SNAPSHOT.jar

FROM unicon/shibboleth-idp:latest

MAINTAINER Unicon, Inc.

COPY shibboleth-idp/ /opt/shibboleth-idp/
COPY shib-jetty-base/ /opt/shib-jetty-base/
COPY --from=0 /malotian.shibboleth.release.attributes.post.processor/target/com.malotian.shibboleth.release.attributes.post.processor-0.0.1-SNAPSHOT.jar /opt/shibboleth-idp/webapp/WEB-INF/lib/
COPY --from=0 /flows /opt/shibboleth-idp/flows/
