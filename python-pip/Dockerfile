# Run python2.7 with packages regardless of host OS
# (built for ease of python package installation in NixOS)
#
# includes: pycrypto, gmpy, numpy, pwntools, PIL
#
# usage: docker run -it pie

FROM ubuntu:latest

# Set the working directory to /app
WORKDIR /app

# Set the current directory contents to a volume mounted at app
VOLUME /app

# install packages, can be customized to user needs
RUN apt-get update
RUN apt-get install -y gcc python python-pip python-gmpy python-numpy 
RUN pip install --upgrade pip
RUN pip install --user pwntools Pillow pycrypto

# start in bash, python can be executed from there
CMD ["/bin/bash"]
