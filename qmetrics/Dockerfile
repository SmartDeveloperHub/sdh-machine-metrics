FROM alejandrofcarrera/phusion.python
MAINTAINER Alejandro F. Carrera

ENV HOME /usr/lib/metrics

# Create directories & virtual env
RUN virtualenv $HOME/.env
WORKDIR /usr/lib/metrics

# Configure runit
ADD ./my_init.d/ /etc/my_init.d/
ONBUILD ./my_init.d/ /etc/my_init.d/

CMD ["/sbin/my_init"]

VOLUME ["/usr/lib/metrics"]

EXPOSE 5006
