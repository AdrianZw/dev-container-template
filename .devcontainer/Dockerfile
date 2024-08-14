FROM ubuntu:24.04
# or required OS
ARG USERNAME=adrianzw
# to be replaced
ARG USER_UID=1000
ARG USER_GID=$USER_UID

ENV DEBIAN_FRONTEND=noninteractive

# Install language
RUN apt-get update \
  && apt-get install -y locales \
  && locale-gen en_US.UTF-8 \
  && update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8

RUN apt-get update
RUN apt-get install -y \
  build-essential\
  git \
  python3 \
  python3-pip
  # add other required packages, e.g. for graphics in
  # older ubuntu distros <= 22.04
  # libgl1-mesa-glx \
  # libgl1-mesa-dri \


# Setup User < 24.04
# RUN groupadd --gid $USER_GID $USERNAME \
#   && useradd -s /bin/bash --uid $USER_UID --gid $USER_GID -m $USERNAME \
#   # [Optional] Add sudo support for the non-root user
#   && apt-get update \
#   && apt-get install -y sudo \
#   && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME\
#   && chmod 0440 /etc/sudoers.d/$USERNAME

RUN usermod -l $USERNAME ubuntu \
  && mkdir -p /home/$USERNAME \
  && chown -R $USERNAME /home/$USERNAME \
  # [Optional] Add sudo support for the non-root user
  && apt-get update \
  && apt-get install -y sudo \
  && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME\
  && chmod 0440 /etc/sudoers.d/$USERNAME


WORKDIR /home/$USERNAME

USER $USERNAME

RUN mkdir -p /home/$USERNAME/ws/
