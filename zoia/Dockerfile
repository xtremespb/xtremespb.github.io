FROM debian
RUN apt-get update && apt-get upgrade -y
RUN apt-get install wget gnupg gnupg2 gnupg1 unzip -y
RUN wget -q -O - https://deb.nodesource.com/setup_8.x | bash
RUN apt-get install nodejs -y
RUN npm i forever -g
RUN mkdir mkdir /usr/local/zoia
RUN wget -q -O - https://xtremespb.github.io/zoia/zoia_install_min | bash
RUN wget -q -O - https://xtremespb.github.io/zoia/zoia_start > /usr/local/bin/zoia
RUN chmod +x /usr/local/bin/zoia
WORKDIR /usr/local/zoia
COPY config.js /usr/local/zoia/etc
COPY website.js /usr/local/zoia/etc
EXPOSE 3000
CMD ["node", "/usr/local/zoia/bin/webserver"]