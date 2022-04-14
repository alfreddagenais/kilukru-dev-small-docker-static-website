# Test 1

Construisez l'image :

```sh
docker build -t my-static-website:test1 .
```

Exécutez l'image :

```sh
docker run -it --rm -p 3000:3000 my-static-website:test1
```
