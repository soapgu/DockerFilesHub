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