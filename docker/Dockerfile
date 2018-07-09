FROM couchdb:2.1.1

ENV PATH=$PATH:/opt/couchdb/bin

# Replace original docker-entrypoint.sh with our custom one
COPY ./docker-entrypoint.sh /
RUN chmod +x /docker-entrypoint.sh && \
    chown -R couchdb:root /opt/couchdb && \
    chmod -R 0770 /opt/couchdb/data && \
    chmod 664 /opt/couchdb/etc/*.ini && \
    chmod 664 /opt/couchdb/etc/local.d/*.ini && \
    chmod 775 /opt/couchdb/etc/*.d

USER 1001
