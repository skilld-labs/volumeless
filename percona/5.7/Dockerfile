FROM percona:5.7

USER root
RUN /usr/bin/install -m 0775 -o mysql -g root -d /data &&\
  sed -Ei 's/(datadir\s*=\s*)(\S*)$/\1\/data/' /etc/percona-server.conf.d/mysqld.cnf &&\
  echo 'max_allowed_packet = 4096M' >> /etc/percona-server.conf.d/mysqld.cnf
USER mysql
