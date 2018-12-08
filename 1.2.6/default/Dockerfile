# Use an official Python runtime as a base image
FROM python:3.6.5-slim-stretch

MAINTAINER Enrico Yang <enrico.j.yang@gmail.com>

# Set Chinese source of pip
RUN mkdir .pip

RUN echo "[global] && \
        index-url = http://pypi.douban.com/simple \
        [install] \
        trusted-host = pypi.douban.com" > .pip/pip.conf

# Install any needed packages specified in requirements.txt
RUN \
    echo "==> Install behave and related stuff..."   && \
    pip3 install --no-cache-dir behave==1.2.6

WORKDIR    /app

# Run app.py when the container launches
ENTRYPOINT ["behave"]