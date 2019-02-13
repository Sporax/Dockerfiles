# Use an official Python runtime as a parent image
FROM debian:latest

# Set the working directory to /app
WORKDIR /app

# Copy the current directory contents into the container at /app
VOLUME /app

RUN apt-get update
RUN apt-get install -y bless sudo && \
	apt-get clean

RUN export uid=1000 gid=1000 && \
    mkdir -p /home/developer && \
    echo "developer:x:${uid}:${gid}:Developer,,,:/home/developer:/bin/bash" >> /etc/passwd && \
    echo "developer:x:${uid}:" >> /etc/group && \
    echo "developer ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/developer && \
    chmod 0440 /etc/sudoers.d/developer && \
    chown ${uid}:${gid} -R /home/developer

USER developer
ENV HOME /home/developer
CMD /usr/bin/bless
