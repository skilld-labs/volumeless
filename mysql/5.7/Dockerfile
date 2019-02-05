FROM mysql:5.7

RUN /usr/bin/install -m 0775 -o mysql -g root -d /data &&\
  find /etc/mysql/ -name '*.cnf' -print0 \
    | xargs -0 grep -lZE '^(datadir)' \
    | xargs -rt -0 sed -Ei 's/(datadir\s*=\s*)(\S*)$/\1\/data/'
