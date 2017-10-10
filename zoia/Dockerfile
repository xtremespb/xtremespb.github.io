FROM debian
RUN apt-get update && apt-get upgrade -y
RUN apt-get install wget gnupg gnupg2 gnupg1 unzip -y
RUN wget -q -O - https://deb.nodesource.com/setup_8.x | bash
RUN apt-get install nodejs -y
RUN npm i forever -g
RUN mkdir mkdir /usr/local/zoia
WORKDIR /usr/local/zoia
RUN wget -q -O - https://xtremespb.github.io/zoia/zoia_install_min | bash
COPY config.js /usr/local/zoia/etc
COPY website.js /usr/local/zoia/etc
EXPOSE 3000
ENTRYPOINT ["forever", "--pidFile", "/usr/local/zoia/run/zoia.pid", "--sourceDir", "/usr/local/zoia/bin", "-l", "/usr/local/zoia/logs/zoia.log", "-a", "--minUptime", "1000", "--spinSleepTime", "1000", "webserver.js"]