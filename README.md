Public mirror of git repository at https://salsa.debian.org/mirror-team/mirror/status

Packages required:
 - alembic
 - postgresql
 - python3-alembic
 - python3-bs4
 - python3-dateutil
 - python3-jinja2
 - python3-psycopg2
 - python3-sqlalchemy

Extra packages required for the `update` script:
 - dpkg-dev (for generate-masterlist-file)
 - python3-debianbts (for get-bug-status)
 - rsync

Quick start
-----------

Setup:

  1. Create a "mirror-status" pg db
  2. "CREATE EXTENSION pgcrypto" as a dbms superuser in the mirror-status database.
  3. Run ./db-create (or alembic upgrade head)

Maintenance:

  1. Run ./import-mirrors --masterlist /path/to/Mirrors.masterlist.in
  2. Run ./run-tests && ./run-process
  3. Run ./generate --outdir /path/to/output/directory
