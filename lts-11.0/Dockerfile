FROM fpco/stack-build:lts-11.0

RUN git clone https://github.com/edenhill/librdkafka .rdkafka && \
      cd .rdkafka && \
      ./configure && \
      make && \
      sudo make install

RUN sudo ln -s /usr/local/lib/librdkafka.so.1 /usr/lib/librdkafka.so.1 && \
      sudo ln -s /usr/local/lib/librdkafka.so /usr/lib/librdkafka.so

RUN stack setup --no-terminal
RUN stack install hlint
