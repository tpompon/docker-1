FROM ubuntu:18.04

WORKDIR minecraft_server

RUN apt-get update && apt-get upgrade -y
RUN apt-get install -y openjdk-8-jre-headless screen wget
RUN wget https://launcher.mojang.com/v1/objects/3737db93722a9e39eeada7c27e7aca28b144ffa7/server.jar -O minecraft_server.1.13.jar
RUN echo "#!/bin/sh" > run.sh && echo "java -Xms1024M -Xmx1536M -jar minecraft_server.1.13.jar -o true" >> run.sh && chmod -x run.sh
RUN /bin/bash run.sh && echo "eula=true" > eula.txt

EXPOSE 25565

ENTRYPOINT /bin/bash run.sh

# 1.13 Minecraft Server
