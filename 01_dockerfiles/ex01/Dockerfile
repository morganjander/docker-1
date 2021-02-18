FROM debian

WORKDIR /home/teamspeak

EXPOSE 9987/udp 10011 30033

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y wget bzip2 && \
    wget http://dl.4players.de/ts/releases/3.13.2/teamspeak3-server_linux_amd64-3.13.2.tar.bz2 && \
    tar -xvf teamspeak3-server_linux_amd64-3.13.2.tar.bz2

WORKDIR teamspeak3-server_linux_amd64

ENTRYPOINT sh ts3server_minimal_runscript.sh

# build: docker build -t ex01 .
# run: docker run -d --name teamspeak -e TS3SERVER_LICENSE=accept -p 9987:9987/udp -p 30033:30033 -p 10011:10011 -p 41144:41144 ex01