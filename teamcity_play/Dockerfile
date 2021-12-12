#base
FROM openjdk:8
ENV PROJECT_HOME /usr/src

WORKDIR $PROJECT_HOME

RUN curl  -LO https://github.com/sbt/sbt/releases/download/v1.5.2/sbt-1.5.2.zip && unzip sbt-1.5.2.zip
ENV PATH $PROJECT_HOME/sbt/bin:$PATH

RUN mkdir $PROJECT_HOME/teamcity_play
COPY . $PROJECT_HOME/teamcity_play
WORKDIR $PROJECT_HOME/teamcity_play
EXPOSE 9000
RUN sbt compile
CMD ["sbt", "run"]