ARG IMAGE
FROM $IMAGE

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get install -y \
    wget curl python3 python3-pip debhelper devscripts \
    libpixman-1-0 libpng16-16 libfdt1 libglib2.0-dev 'libjson-c[34]' libyajl2 libaio1 lsb-release && \
    curl "https://debs.icedev.pl/manual/dh-virtualenv/$(lsb_release -cs)/dh-virtualenv_1.2~dev-1_all.deb" -o dh-virtualenv.deb && \
    pip3 install virtualenv && \
    apt install -y ./dh-virtualenv.deb

RUN wget -O drakvuf.deb "https://debs.icedev.pl/manual/drakvuf-bundle/$(lsb_release -cs)/drakvuf-bundle-0.7-git20200501075508+0f828ce-1.deb" && \
    apt install -y ./drakvuf.deb

COPY drakrun /build
WORKDIR /build
