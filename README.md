Don't forget to change the namespace and path or other configuration as you need

To deploy seafile-testing-v4-final-with-secret.yaml you must create a secret for seafile_db and seafile_server.

Follow this command :

# Seafile Database Secret
    kubectl create secret generic seafile-db-secret -n seafile-testing \
    --from-literal=MYSQL_ROOT_PASSWORD=changeme

# Seafile Server Secret
    kubectl create secret generic seafile-server-secret -n seafile-testing \
    --from-literal=DB_ROOT_PASSWD=changeme \
	--from-literal=SEAFILE_ADMIN_EMAIL=admin@email.com \
	--from-literal=SEAFILE_ADMIN_PASSWORD=changeme

And if you want to testing from your local you have to change the SERVICE_URL and FILE_SERVER_ROOT with port you use to forward from service.

Example :

![IMAGE_DESCRIPTION](https://raw.githubusercontent.com/kepps-usr/seafile-kubernetes/main/img/example.png)
