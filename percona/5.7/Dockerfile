FROM percona:5.7

USER root
RUN /usr/bin/install -m 0775 -o mysql -g root -d /data &&\
  find /etc/percona-server.conf.d/ -name '*.cnf' -print0 \
    | xargs -0 grep -lZE '^(datadir)' \
    | xargs -rt -0 sed -Ei 's/(datadir\s*=\s*)(\S*)$/\1\/data/'
USER mysql
