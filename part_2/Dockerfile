FROM gcc:11.2.0
ENV REFRESHED_AT 4-02-2022
RUN apt-get -qq update \
	&& apt-get -y install git cmake
WORKDIR /usr/project
# CMD [ "sh", "-c", "cmake", "-B", "$(pwd)/build", "-S", "$(pwd)", "&&", "cmake", "--build", "build" ]
CMD cmake -B build -S . && cmake --build build

