# Categorizador de Palavras

## Requisitos

- Java 11
- Docker
- Docker Compose

## Executar


Subir ambiente do kafka, na raiz do projeto execute o seguinte comando:

```
$ docker-compose up
```

Ainda na raiz do projeto execute a aplicação em spring boot com o seguinte comando, no seu terminal:

```
$ ./mwvn clean spring-boot:run
```

Agora para testar na raiz do projeto execute o seguinte comando abaixo, então escreva as mensagens que irão gerar os eventos

```
$ docker-compose exec kafka kafka-console-producer --bootstrap-server localhost:9092 --topic entrada
>test
>123
>
```

Para finalizar, para consultar as mensagens rode na raiz do projeto os seguintes comando:

```
$ docker-compose exec kafka kafka-console-consumer --bootstrap-server localhost:9092 --topic pequenas --from-beginning
```

```
$ docker-compose exec kafka kafka-console-consumer --bootstrap-server localhost:9092 --topic medias --from-beginning
```

``` 
$ docker-compose exec kafka kafka-console-consumer --bootstrap-server localhost:9092 --topic grandes --from-beginning
```