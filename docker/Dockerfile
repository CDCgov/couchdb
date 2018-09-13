FROM couchdb:2.2.0

# Replace original docker-entrypoint.sh with our custom one
COPY ./docker-entrypoint.sh /
RUN chmod +x /docker-entrypoint.sh && \
    chown -R couchdb:root /opt/couchdb && \
    chmod -R 0770 /opt/couchdb/data && \
    find /opt/couchdb/etc -name \*.ini -exec chmod -f 664 {} \; && \
    chmod 775 /opt/couchdb/etc/*.d

USER 1001
