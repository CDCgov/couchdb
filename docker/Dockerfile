FROM couchdb:1.6.1

# Replace original docker-entrypoint.sh with our custom one
COPY ./docker-entrypoint.sh /
RUN chmod +x /docker-entrypoint.sh && \
    chgrp -R root /usr/local/var/lib/couchdb \
                  /usr/local/var/log/couchdb \
                  /usr/local/var/run/couchdb \
                  /usr/local/etc/couchdb && \
    chmod -R 0770 /usr/local/var/lib/couchdb \
                  /usr/local/var/log/couchdb \
                  /usr/local/var/run/couchdb \
                  /usr/local/etc/couchdb && \
    chmod 664 /usr/local/etc/couchdb/*.ini && \
    chmod 775 /usr/local/etc/couchdb/*.d

USER 1001
