FROM mysql:5.7

RUN /usr/bin/install -m 0775 -o mysql -g root -d /data &&\
  sed -Ei 's/(datadir\s*=\s*)(\S*)$/\1\/data/' /etc/mysql/mysql.conf.d/mysqld.cnf &&\
  echo 'max_allowed_packet = 4096M' >> /etc/mysql/mysql.conf.d/mysqld.cnf
