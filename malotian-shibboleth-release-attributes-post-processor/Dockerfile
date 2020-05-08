FROM maven:3.6.3-jdk-11
RUN git clone https://github.com/malotian/malotian.shibboleth.release.attributes.post.processor.git malotian.shibboleth.release.attributes.post.processor
RUN mvn -f malotian.shibboleth.release.attributes.post.processor/pom.xml install
ENTRYPOINT ["uname"]
