FROM debian

EXPOSE 9987/udp 30033/tcp 10011/tcp

ENV TS3SERVER_LICENSE=accept

WORKDIR /home/teamspeak

RUN apt update && \
    apt upgrade -y && \
    apt install -y wget bzip2 && \
    wget https://files.teamspeak-services.com/releases/server/3.9.1/teamspeak3-server_linux_amd64-3.9.1.tar.bz2 && \
    tar xvjf teamspeak3-server_linux_amd64-3.9.1.tar.bz2 && \
    rm teamspeak3-server_linux_amd64-3.9.1.tar.bz2

WORKDIR teamspeak3-server_linux_amd64

ENTRYPOINT sh ts3server_minimal_runscript.sh
  
# Useful links
# - - - - - - -
# https://teamspeak.com/en/downloads/#server
# https://console.nodilex.com/fr/community/tutorials/13/installer-un-serveur-vocal-teamspeak-3-sur-linux-debian-ubuntu/

# 9987/udp for Voice.
# 30033/tcp for Filetransfer.
# 10011/tcp for ServerQuery.

# docker build -t teamspeak-debian .
# docker run -p 9987:9987/udp -p 30033:30033/tcp -p 10011:10011/tcp teamspeak-debian
