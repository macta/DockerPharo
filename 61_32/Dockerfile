FROM macta/pharo:base_32

LABEL description="A small Pharo 32bit environment base on Ubuntu 16.04" \
      keywords="smalltalk, pharo" \
      version="1.0"

RUN mkdir -p /opt/pharo &&\
        cd /opt/pharo &&\
        curl https://get.pharo.org/61+vm | bash &&\
        ln -s \
            `/sbin/ldconfig -p | grep -v x86-64 | sed -e 's|[^/]*||' | grep sqlite3` \
            `find . -type f -name SqueakSSL.so -print0 | xargs -0 dirname`/sqlite3.so

RUN cd /usr/local/bin && ln -s /opt/pharo/pharo && ln -s /opt/pharo/pharo-ui

RUN pharo /opt/pharo/Pharo.image eval  "'Pharo {1}bit installed\' format: {32}"
