FROM debian
RUN
  apt update -y && apt upgrade -y && \
  apt install wget b2zip && \
  adduser teamspeak && su teamspeak && \
  cd /home/teamspeak && \
  wget https://files.teamspeak-services.com/releases/server/3.9.1/teamspeak3-server_linux_amd64-3.9.1.tar.bz2 && \
  tar xvjf teamspeak3-server_linux_amd64-3.9.1.tar.bz2 && \
  rm teamspeak3-server_linux_amd64-3.9.1.tar.bz2 && \
  cd teamspeak3-server_linux_amd64 && \
  echo "license_accepted=1" > .ts3server_license_accepted && \
  ./ts3server_minimal_runscript.sh createinifile=1
  
  
# Useful links
# - - - - - - -
# https://teamspeak.com/en/downloads/#server
# https://console.nodilex.com/fr/community/tutorials/13/installer-un-serveur-vocal-teamspeak-3-sur-linux-debian-ubuntu/
