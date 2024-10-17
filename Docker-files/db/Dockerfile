FROM mysql:8.0.33
LABEL "project"="MYvprofile"
LABEL "Author"="Greynalytics"

ENV MYSQL_ROOT_PASSWORD="SirGrey"
ENV MYSQL_DATABASE="accounts"

ADD db_backup.sql docker-entrypoint-initdb.d/db_backup.sql