FROM        --platform=$TARGETOS/$TARGETARCH bellsoft/liberica-openjdk-alpine:17

LABEL       author="FnlTochka" maintainer="me@fnltochka.ru"

LABEL       org.opencontainers.image.source="https://github.com/FnlTochka/gravitlauncher-yolks"
LABEL       org.opencontainers.image.licenses=MIT

RUN 		apt-get update -y \
	&& apt-get install -y lsof curl ca-certificates openssl git tar sqlite3 fontconfig libfreetype6 tzdata iproute2 libstdc++6 \
	&& useradd -d /home/container -m container

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./../entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]
