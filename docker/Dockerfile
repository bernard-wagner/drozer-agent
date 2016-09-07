FROM ubuntu:latest
MAINTAINER Bernard Wagner

RUN apt-get update && apt-get install -y lib32z1 lib32ncurses5 lib32stdc++6 openjdk-8-jdk unzip wget build-essential

WORKDIR /tmp

RUN wget http://dl.google.com/android/repository/build-tools_r24.0.2-linux.zip -O /tmp/build-tools.zip && \
    unzip /tmp/build-tools.zip && \
    rm /tmp/build-tools.zip && \
    mkdir -p /usr/lib/android-sdk-linux/build-tools/ && \
    mv android-7.0 /usr/lib/android-sdk-linux/build-tools/24.0.2

RUN wget http://dl.google.com/android/repository/android-16_r05.zip -O /tmp/android-16.zip && \
    unzip android-16.zip && \
    rm android-16.zip && \
    mkdir -p /usr/lib/android-sdk-linux/platforms/ && \
    mv android-4.1.2 /usr/lib/android-sdk-linux/platforms/android-16

RUN wget http://dl.google.com/android/repository/android-ndk-r12b-linux-x86_64.zip -O /tmp/android-ndk.zip && \
    unzip  android-ndk.zip && \
    rm android-ndk.zip && \
    mv android-ndk-r12b /usr/lib/android-sdk-linux/ndk

ENV ANDROID_HOME=/usr/lib/android-sdk-linux/
ENV ANDROID_NDK_HOME=/usr/lib/android-sdk-linux/ndk/
