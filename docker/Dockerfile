FROM couchdb:2.1.1

# Replace original docker-entrypoint.sh with our custom one
COPY ./docker-entrypoint.sh /
RUN chmod +x /docker-entrypoint.sh && \
    chown -R couchdb:root /opt/couchdb && \
    chmod -R 0770 /opt/couchdb/data && \
    chmod 664 /opt/couchdb/etc/*.ini && \
    chmod 775 /opt/couchdb/etc/*.d \
              /opt/couchdb/var/log

# enable debug logging temporarily
RUN sed -i -e "/^level/ {c \
level = debug
}" /opt/couchdb/etc/default.ini
USER 1001
