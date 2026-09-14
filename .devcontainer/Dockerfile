FROM mcr.microsoft.com/devcontainers/java:1-17-bookworm

# install dependencies
RUN apt-get purge --auto-remove yarn || true
RUN rm /etc/apt/sources.list.d/yarn.list || true
RUN apt-get update && apt-get upgrade -y
RUN apt-get install -y python3-pip git-lfs
RUN pip3 install --break-system-packages requests

# download WPILib extension
COPY ./get-wpilib.py /opt
RUN python3 /opt/get-wpilib.py