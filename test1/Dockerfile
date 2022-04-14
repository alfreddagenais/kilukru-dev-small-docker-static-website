FROM alfreddagenais/small-docker-static-website:latest

# Copiez vos fichiers statiques
COPY . .

CMD ["/thttpd", "-D", "-h", "0.0.0.0", "-p", "3000", "-d", "/home/static", "-u", "static", "-l", "-", "-M", "60"]