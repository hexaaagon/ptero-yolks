FROM        --platform=$TARGETOS/$TARGETARCH node:16-bullseye-slim

LABEL       author="Hexagonn" maintainer="me@hexagonn.my.id"

RUN         apt update \
            && apt -y install ffmpeg iproute2 git sqlite3 libsqlite3-dev python3 ca-certificates dnsutils tzdata zip tar curl build-essential libtool fonts-liberation libappindicator3-1 libasound2 libatk-bridge2.0-0 libatk1.0-0 libc6 libcairo2 libcups2 libdbus-1-3 libexpat1 libfontconfig1 libgbm1 libgcc1 libglib2.0-0 libgtk-3-0 libnspr4 libnss3 libpango-1.0-0 libpangocairo-1.0-0 libstdc++6 libx11-6 libx11-xcb1 libxcb1 libxcomposite1 libxcursor1 libxdamage1 libxext6 libxfixes3 libxi6 libxrandr2 libxrender1 libxss1 libxtst6 lsb-release wget xdg-utils --no-install-recommends libgconf-2-4 libgdk-pixbuf2.0-0 gconf-service \
            && npm -g install npm@latest \
            && useradd -m -d /home/container container \
			&& python3 -m pip install -U demucs so-vits-svc-fork ipython
			
USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./../entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]
