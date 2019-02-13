# Use an official Python runtime as a parent image
FROM debian:latest

# Set the working directory to /app
WORKDIR /app

# Copy the current directory contents into the container at /app
VOLUME /app

RUN apt-get update
RUN apt-get install -y sudo texlive texlive-xetex

# Use somebody as a regular user
RUN export uid=1000 gid=1000 && \
    mkdir -p /home/somebody && \
    echo "somebody:x:${uid}:${gid}:Developer,,,:/home/somebody:/bin/bash" >> /etc/passwd && \
    echo "somebody:x:${uid}:" >> /etc/group && \
    echo "somebody ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/somebody && \
    chmod 0440 /etc/sudoers.d/somebody && \
    chown ${uid}:${gid} -R /home/somebody

USER somebody
ENV HOME /home/somebody
CMD ["/bin/bash"]
