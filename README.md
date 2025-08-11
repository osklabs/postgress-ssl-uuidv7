# SSL-enabled Postgres DB image with `pg_uuidv7` plugin.

This repository contains a Dockerfile to add the [pg_uuidv7](https://github.com/fboulnois/pg_uuidv7) plugin to [Railway's SSL-Enabled Postgres](https://github.com/railwayapp-templates/postgres-ssl) image.

## Usage

You can use the pre-built image for postgres-ssl (17) and pg_uuidv7 (1.6.0)

```bash
docker pull ghcr.io/osklabs/postgres-ssl-uuidv7:17-1.6.0
```

For development, the pre-built image with only `pg_uuidv7` can be used:

```bash
docker pull ghcr.io/fboulnois/pg_uuidv7:1.6.0
```

In postgres, initialize the plugin:

```sql
CREATE EXTENSION pg_uuidv7;
```

From there, you can generate [version 7 UUIDs](https://www.ietf.org/archive/id/draft-ietf-uuidrev-rfc4122bis-00.html#name-uuid-version-7) in Postgres:

```sql
SELECT uuid_generate_v7();

           uuid_generate_v7
--------------------------------------
 018570bb-4a7d-7c7e-8df4-6d47afd8c8fc
(1 row)
```

For additional usages, refer to the [original repository of the plugin](https://github.com/fboulnois/pg_uuidv7).
