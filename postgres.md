# Replace a postgres database from a file

$USER = username
$DATABASE = db-name

psql -U $USER -h localhost -c "DROP DATABASE $DATABASE"
psql -U $USER -h localhost -c "CREATE DATABASE $DATABASE"
pg_restore --verbose --clean --no-acl --no-owner -h localhost -U $USER -d $DATABASE latest.dump

