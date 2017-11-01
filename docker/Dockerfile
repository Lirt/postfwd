FROM debian:stretch-slim

LABEL maintainer="Postfwd Docker Maintainer <info@jpkessler.de>"

RUN apt-get update && \
    apt-get install -y postfwd

ARG PORT=10040

RUN mkdir /etc/postfwd
VOLUME /etc/postfwd

EXPOSE $PORT

COPY docker-entrypoint.sh /opt/docker-entrypoint.sh
ENTRYPOINT ["/opt/docker-entrypoint.sh"]

CMD ["/usr/sbin/postfwd2", \
     "--file", "/etc/postfwd/postfwd.cf", \
     "--user", "postfw", \
     "--group", "postfw", \
     "--stdout"]
