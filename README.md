   # Anotações sobre Docker

## basics

### Listar as parada do começo

```
docker ps
```

### criar um novo container NGINX

```
docker run nginx
```

### linkar porta da aplicação a porta do nginx

```
docker run -p 8080:80 nginx
```

significa que o server com porta 8080 direciona para a porta 80 do nginx

### listar diretorios do container

```
docker exec adoring_kowalevski ls
```

## for devs

### compartilhando pasta do pc com o container

```
docker run -p 8080:80 -v $(pwd)/html:/usr/share/nginx/html nginx
```

### gerando a propria imagem

crie um arquivo Dockerfile

raiz
   - Dockerfile

dentro dele adicione

```
FROM nginx:latest

COPY {endereço do seu arquivo} /usr/share/nginx/html/
```

```
docker build -t lpxsbr/nginx-aula:latest .
```

### para rodar a imagem criada no docker

```
docker run -p 8080:80 lpxsbr/nginx-aula:latest
```

### para publicar no docker

```
docker push lpxsbr/nginx-aula:latest
```

## Arquivo YAML

Manifesto de todos os containers pra rodar

##

History

```
lpxsbr/nginx-pomodoro:latest
```