FROM debian:buster-slim

RUN rm /etc/apt/sources.list && \
    echo "deb http://mirrors.163.com/debian/ buster main non-free contrib" >/etc/apt/sources.list && \
    echo "deb http://mirrors.163.com/debian/ buster-updates main non-free contrib" >>/etc/apt/sources.list && \
    echo "deb-src http://mirrors.163.com/debian/ buster main non-free contrib" >>/etc/apt/sources.list && \
    echo "deb-src http://mirrors.163.com/debian/ buster-updates main non-free contrib" >>/etc/apt/sources.list && \
	echo "deb http://mirrors.163.com/debian-security/ buster/updates main non-free contrib" >>/etc/apt/sources.list && \
	echo "deb-src http://mirrors.163.com/debian-security/ buster/updates main non-free contrib" >>/etc/apt/sources.list

RUN apt update
RUN mkdir -p /usr/share/man/man1
RUN yes | apt install openjdk-11-jre-headless
RUN yes | apt install unzip
RUN yes | apt install git
RUN yes | apt install curl
RUN mkdir /andriod
WORKDIR /andriod

# 解压android tools
RUN curl -O https://dl.google.com/android/repository/commandlinetools-linux-7583922_latest.zip
RUN unzip -d /andriod commandlinetools-linux-7583922_latest.zip

# install sdk
ENV ANDROID_SDK_ROOT /opt/app/android-sdk
RUN mkdir -p $ANDROID_SDK_ROOT
RUN yes | /andriod/cmdline-tools/bin/sdkmanager --list --sdk_root=$ANDROID_SDK_ROOT
RUN yes | /andriod/cmdline-tools/bin/sdkmanager "platforms;android-30" "build-tools;30.0.3" --sdk_root=$ANDROID_SDK_ROOT

# clean
RUN rm commandlinetools-linux-7583922_latest.zip
RUN rm -rf cmdline-tools