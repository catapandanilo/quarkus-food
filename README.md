# Tutorial: Criando um CRUD utilizando Quarkus Java + REST + CDI + Panache, Hibernate com Postgres (Docker) + Postman

## Link para os Artigos
- [Linkedin Pulse](https://www.linkedin.com/pulse/tutorial-criando-um-crud-utilizando-quarkus-java-rest-da-silva-melo/) : https://www.linkedin.com/pulse/tutorial-criando-um-crud-utilizando-quarkus-java-rest-da-silva-melo/

- [Medium](https://medium.com/@marcus.paulo/tutorial-criando-um-crud-utilizando-quarkus-java-rest-cdi-panache-hibernate-com-postgres-59793e0d7162) : https://medium.com/@marcus.paulo/tutorial-criando-um-crud-utilizando-quarkus-java-rest-cdi-panache-hibernate-com-postgres-59793e0d7162

### Estrutura de Arquivos

A estrutura de arquivos está da seguinte maneira:

```bash
quarkus-food
├── README.md
├── pom.xml
├── quarkus-food.iml
└── src
    ├── main
    │   ├── docker
    │   │   ├── Dockerfile.jvm
    │   │   └── Dockerfile.native
    │   ├── java
    │   │   └── br
    │   │       └── com
    │   │           └── food
    │   │               ├── controller
    │   │               │   └── FoodController.java
    │   │               ├── entity
    │   │               │   └── Food.java
    │   │               └── resource
    │   │                   └── FoodResource.java
    │   └── resources
    │       ├── META-INF
    │       │   └── resources
    │       │       └── index.html
    │       └── application.properties
    └── test
        └── java
            └── br
                └── com
                    └── food
                        └── resource
                            ├── FoodResourceTest.java
                            └── NativeFoodResourceIT.java

19 directories, 12 files
```

#### Executando a Instância do Postgresql no Docker

Para iniciar o Postgresql, basta rodar o comando abaixo (O Docker precisa estar instalado):

```sh
docker run --name postgres-food -e "POSTGRES_PASSWORD=postgres" -p 5433:5432 -v ~/developer/PostgreSQL:/var/lib/postgresql/data -d postgres
```

### Executando o projeto em Quarkus

Para executar um projeto em Quarkus, basta executar o comando:
```sh
mvn compile quarkus:dev
```