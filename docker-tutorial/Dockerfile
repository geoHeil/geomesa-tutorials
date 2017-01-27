FROM buildpack-deps:xenial-scm
MAINTAINER Georg Heiler <georg.heiler@t-mobile.at>

RUN apt-get update && apt-get install -y --no-install-recommends \
		maven \
		openjdk-8-jdk

ENV LANG C.UTF-8
ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64

RUN git clone https://github.com/geoHeil/geomesa-tutorials.git
WORKDIR geomesa-tutorials
RUN mvn clean install -pl geomesa-quickstart-accumulo
# TODO cleanup m2 folder

# hack to keep it running
ENTRYPOINT ["top", "-b"]
CMD ["-c"]