# Springpetclinic:

FROM amazoncorretto:17
LABEL author="khaja"
LABEL project="learning"

ARG DOWNLOAD_URL="https://referenceappslt.s3.ap-south-1.amazonaws.com/spring-petclinic-3.3.0-SNAPSHOT.jar"
ARG USER="spc"
ARG GROUP="spc"
ARG UID=1000
ARG GID=1000
ARG HOMEDIR="/spc"

# Install tools for user management
RUN yum install -y shadow-utils \
    && groupadd -g ${GID} ${GROUP} \
    && useradd -d ${HOMEDIR} -u ${UID} -g ${GROUP} -s /bin/bash ${USER}

USER ${USER}

ADD --chown=${USER}:${GROUP} ${DOWNLOAD_URL} ${HOMEDIR}/spring-petclinic-3.3.0-SNAPSHOT.jar
WORKDIR ${HOMEDIR}
EXPOSE 8080
CMD ["java", "-jar", "spring-petclinic-3.3.0-SNAPSHOT.jar"]
