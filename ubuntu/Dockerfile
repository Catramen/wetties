FROM ubuntu

ADD ./wetty /wetty
WORKDIR /wetty

RUN apt-get update 
RUN apt-get install -y nodejs-legacy
RUN apt-get install -y npm
RUN apt-get install -y sudo 
RUN apt-get install -y git && apt-get install -y g++
RUN apt-get install -y make && apt-get install -y python
RUN npm install
RUN useradd -d /home/term -m -s /bin/bash term
RUN echo 'term:term' | chpasswd
RUN usermod -aG sudo term 

VOLUME /usr/local/

EXPOSE 3000

# Define default command.
ENTRYPOINT ["node"]
CMD ["app.js", "-p", "3000"]


