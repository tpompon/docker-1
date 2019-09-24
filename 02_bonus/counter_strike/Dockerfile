FROM debian

RUN dpkg --add-architecture i386
RUN apt-get update && apt-get upgrade -y
RUN apt-get install gcc-multilib libstdc++6:i386 libgcc1:i386 zlib1g:i386 libncurses5:i386 libc6:i386 wget screen

WORKDIR steam

RUN wget http://media.steampowered.com/client/steamcmd_linux.tar.gz && tar xfvz steamcmd_linux.tar
RUN /bin/bash steamcmd.sh +login anonymous +force_install_dir ./csgo_server +app_update 740 validate +quit

WORKDIR csgo_server

ENTRYPOINT ./srcds_run -game csgo -console -usercon +game_type 0 +game_mode 0 +mapgroup mg_bomb +map de_dust

# Need more than 15 GB hard disk space
