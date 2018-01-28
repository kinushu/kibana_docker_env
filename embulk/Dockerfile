FROM java:8

# system update
RUN apt-get -y update && apt-get -y upgrade

# locale
RUN apt-get -y install locales && \
    localedef -f UTF-8 -i ja_JP ja_JP.UTF-8
ENV LANG ja_JP.UTF-8
ENV LANGUAGE ja_JP:ja
ENV LC_ALL ja_JP.UTF-8

# timezone (Asia/Tokyo)
ENV TZ JST-9

# etc
ENV TERM xterm

# tools
RUN apt-get install -y vim git zip unzip less wget

# embulk
RUN curl -o /usr/local/bin/embulk --create-dirs -L "http://dl.embulk.org/embulk-latest.jar" && \
    chmod +x /usr/local/bin/embulk

RUN embulk gem install embulk-parser-ltsv
RUN embulk gem install embulk-output-elasticsearch
RUN embulk gem install embulk-filter-ruby_proc

RUN mkdir /works/
WORKDIR /works/
ENTRYPOINT ["/bin/sh", "-c", "while true; do echo embulk turn on; sleep 60; done"]
