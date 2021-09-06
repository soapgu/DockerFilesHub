FROM soapgu/android-sdk-slim:v1.0

WORKDIR /
RUN git clone https://github.com/soapgu/DockerBuildApk.git andriod
WORKDIR /andriod
RUN chmod +x ./gradlew
RUN ./gradlew tasks