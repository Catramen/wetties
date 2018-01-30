FROM alpine 

ADD ./wetty /wetty
WORKDIR /wetty

RUN apk update && apk add nodejs
RUN apk add alpine-sdk
RUN apk add git && apk add g++
RUN apk add make && apk add python
RUN npm install
RUN adduser -D term
RUN echo 'term:p@ssw0rd' | chpasswd
RUN echo "term ALL=(ALL) ALL" > /etc/sudoers

VOLUME /usr/local/

EXPOSE 3000

# Define default command.
ENTRYPOINT ["node"]
CMD ["app.js", "-p", "3000"]

