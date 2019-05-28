FROM containers.ssii.com/base/openjdk:11-jre-slim

VOLUME /tmp

ADD @project.build.finalName@.jar @project.build.finalName@.jar

RUN sh -c 'touch /@project.build.finalName@.jar'

ENV JAVA_OPTS="-Xdebug -XshowSettings:vm -XX:+UseContainerSupport -XX:+UnlockExperimentalVMOptions"

CMD exec java $JAVA_OPTS -Djava.security.egd=file:/dev/./urandom -Dspring.profiles.active=docker -jar /@project.build.finalName@.jar