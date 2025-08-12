FROM ghcr.io/fboulnois/pg_uuidv7:1.6.0 AS postgres-uuidv7

FROM postgres:17

# Copy tarball and checksums
COPY --from=0 /srv/pg_uuidv7.tar.gz /srv/SHA256SUMS /srv/

# Add extension to postgres
COPY --from=0 /usr/lib/postgresql/${PG_MAJOR}/lib/pg_uuidv7.so /usr/lib/postgresql/${PG_MAJOR}/lib
COPY --from=0 /usr/share/postgresql/${PG_MAJOR}/extension/pg_uuidv7.control /usr/share/postgresql/${PG_MAJOR}/extension
COPY --from=0 /usr/share/postgresql/${PG_MAJOR}/extension/pg_uuidv7--1.6.sql /usr/share/postgresql/${PG_MAJOR}/extension