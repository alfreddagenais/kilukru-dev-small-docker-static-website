# La plus petite image Docker pour des sites web statiques

Ce dépôt est le résultat de l'article : "La plus petite image Docker pour des sites web statiques". Vous pouvez le consulter sur [kilukru.dev](https://www.kilukru.dev/la-plus-petite-image-docker-pour-des-sites-web-statiques/)

Une image Docker très petite (~200Ko) pour faire fonctionner n'importe quel site web statique, basée sur le serveur de fichiers statiques [thttpd](https://www.acme.com/software/thttpd/).

## Utilisation

L'image est hébergée sur [Docker Hub](https://hub.docker.com/r/alfreddagenais/small-docker-static-website):

```dockerfile
FROM alfreddagenais/small-docker-static-website:latest

# Copiez vos fichiers statiques
COPY . .
```

Construisez l'image :

```sh
docker build -t my-static-website:latest .
```

Exécutez l'image :

```sh
docker run -it --rm -p 3000:3000 my-static-website:latest
```

Naviguer vers `http://localhost:3000`.

Si vous avez besoin de configurer le serveur d'une manière différente, vous pouvez remplacer la ligne `CMD` :

```dockerfile
FROM alfreddagenais/small-docker-static-website:latest

# Copiez vos fichiers statiques
COPY . .

CMD ["/thttpd", "-D", "-h", "0.0.0.0", "-p", "3000", "-d", "/home/static", "-u", "static", "-l", "-", "-M", "60"]
```

## Publication

Tout d'abord, il vous faudra avoir un compte Hub Docker. Créez-vous un repos et vous pourrez ainsi déployer vos images.

Pour Tag une image dans docker

```sh
docker tag my-static-website:latest alfreddagenais/small-docker-static-website:latest
```

Pour publier l'image dans votre Hub Docker

```sh
docker push alfreddagenais/small-docker-static-website:latest
```

## Contact

- [Web](https://alfreddagenais.com/)
- [Blogue](https://www.kilukru.dev/)
- [Linkedin](https://linkedin.com/in/AlfredDagenais)
- [Twitter](https://twitter.com/ProgrammeurWeb)
- [GitHub](https://github.com/alfreddagenais/)
- [Instagram](https://instagram.com/alfreddagenaisweb)
