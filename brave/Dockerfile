### install brave browser in debian container
#
# usage:
# docker run --rm -it -u nobody aziei/brave
# 

FROM debian:jessie

# get wget
RUN apt update && apt install -y wget apt-transport-https --no-install-recommends
RUN apt install -y --force-yes ca-certificates
# add key
RUN wget -O - https://s3-us-west-2.amazonaws.com/brave-apt/keys.asc | apt-key add -
# add pkg
RUN echo "deb [arch=amd64] https://s3-us-west-2.amazonaws.com/brave-apt jessie main" | tee -a /etc/apt/sources.list.d/brave-jessie.list
# install brave
RUN apt update && apt install -y brave
