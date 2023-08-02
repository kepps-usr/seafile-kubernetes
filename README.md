to deploy seafile-testing-v4-final-with-secret.yaml you must create a secret for seafile_db and seafile_server

follow this command :

# Seafile Database Secret
    kubectl create secret generic seafile-db-secret -n seafile-testing \
    --from-literal=MYSQL_ROOT_PASSWORD=changeme

# Seafile Server Secret
    kubectl create secret generic seafile-server-secret -n seafile-testing \
    --from-literal=DB_ROOT_PASSWD=changeme \
	--from-literal=SEAFILE_ADMIN_EMAIL=admin@email.com \
	--from-literal=SEAFILE_ADMIN_PASSWORD=changeme
