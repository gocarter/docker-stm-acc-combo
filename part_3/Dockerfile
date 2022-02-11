FROM gcc:10.3.0

ENV REFRESHED_AT 11-02-2022

RUN apt-get -qq update \
	&& apt-get -y install git python3-pip

RUN pip3 install --system --compile cmake

# Set up a tools dev directory
WORKDIR /home/dev

# Pull the gcc-arm-none-eabi tarball
RUN wget https://developer.arm.com/-/media/Files/downloads/gnu-rm/10.3-2021.10/gcc-arm-none-eabi-10.3-2021.10-x86_64-linux.tar.bz2 \
  && tar xvf gcc-arm-none-eabi-10.3-2021.10-x86_64-linux.tar.bz2 \
  && rm gcc-arm-none-eabi-10.3-2021.10-x86_64-linux.tar.bz2

# Set up the compiler path
ENV PATH $PATH:/home/dev/gcc-arm-none-eabi-10.3-2021.10/bin

WORKDIR /usr/project

CMD cmake -B build -S . && cmake --build build

