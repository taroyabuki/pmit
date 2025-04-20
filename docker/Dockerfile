# ベースイメージ
FROM ubuntu:24.04

# 非対話モード
ENV DEBIAN_FRONTEND=noninteractive

# 必要パッケージ
RUN apt-get update && \
  apt-get install -y --no-install-recommends \
    git apache2 libapache2-mod-php php-mbstring \
    mariadb-server mariadb-client debconf-utils && \
  apt-get clean && rm -rf /var/lib/apt/lists/*

# Apache 警告抑制
RUN echo 'ServerName localhost' >> /etc/apache2/apache2.conf

# MariaDB 初期設定
RUN service mariadb start && \
  sleep 5 && \
  mysql -e "CREATE USER IF NOT EXISTS 'testuser'@'localhost' IDENTIFIED BY 'pass'; \
    GRANT ALL PRIVILEGES ON *.* TO 'testuser'@'localhost'; \
    FLUSH PRIVILEGES;"

# phpMyAdmin の事前回答
RUN { \
  echo 'phpmyadmin phpmyadmin/dbconfig-install boolean true'; \
  echo 'phpmyadmin phpmyadmin/app-password-confirm password '; \
  echo 'phpmyadmin phpmyadmin/mysql/admin-pass password '; \
  echo 'phpmyadmin phpmyadmin/mysql/app-pass password '; \
  echo 'phpmyadmin phpmyadmin/reconfigure-webserver multiselect apache2'; \
} | debconf-set-selections && \
  service mariadb start && \
  apt-get update && apt-get install -y --no-install-recommends phpmyadmin

# 起動スクリプト
RUN cat <<'EOF' >/usr/local/bin/start.sh
#!/usr/bin/env bash
set -e
echo "Starting MariaDB..."
service mariadb start
echo "Starting Apache (foreground)..."
exec apachectl -D FOREGROUND
EOF
RUN chmod +x /usr/local/bin/start.sh

EXPOSE 80
ENTRYPOINT ["/usr/local/bin/start.sh"]

# docker build -t pm-lamp .
# docker tag pm-lamp taroyabuki/pm-lamp:latest
# docker push taroyabuki/pm-lamp:latest
