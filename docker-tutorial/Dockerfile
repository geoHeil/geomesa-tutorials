FROM openjdk:8-jdk
MAINTAINER Georg Heiler <georg.heiler@t-mobile.at>

RUN apt-get update && \
 apt-get install -y git maven


RUN git clone https://github.com/geoHeil/geomesa-tutorials.git
WORKDIR geomesa-tutorials
RUN mvn clean install -pl geomesa-quickstart-accumulo

# hack to keep it running
ENTRYPOINT ["top", "-b"]
CMD ["-c"]