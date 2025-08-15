# Desafio SpringBoot APIREST + Railway

RESTful API da Santander Dev Week 2023 modificado à partir de ideias autorais para teste prático de conhecimentos do curso da DIO - Java Backend.

## Principais Tecnologias
 - **Java 21**: Utilizaremos a versão LTS mais recente do Java para tirar vantagem das últimas inovações que essa linguagem robusta e amplamente utilizada oferece;
 - **Spring Boot 3**: Trabalharemos com a mais nova versão do Spring Boot, que maximiza a produtividade do desenvolvedor por meio de sua poderosa premissa de autoconfiguração;
 - **Spring Data JPA**: Exploraremos como essa ferramenta pode simplificar nossa camada de acesso aos dados, facilitando a integração com bancos de dados SQL;
 - **OpenAPI (Swagger)**: Vamos criar uma documentação de API eficaz e fácil de entender usando a OpenAPI (Swagger), perfeitamente alinhada com a alta produtividade que o Spring Boot oferece;
 - **Railway**: facilita o deploy e monitoramento de nossas soluções na nuvem, além de oferecer diversos bancos de dados como serviço e pipelines de CI/CD.

## Diagrama de Classes (Domínio da API)

```mermaid
classDiagram
  class User {
    -String icon
    -String name
    -Account account
    -Adventures[] adventures
    -Card card
    -BasicUser[] connections
    -News[] news
    -Trophies[] trophies
    -Skills[] skills
    -Travel travel
    -Hometown hometown
    -Transfer[] history
  }

  class Account {
    -String number
    -String agency
    -Number balance
    -Number limit
  }

  class Adventures {
    -String icon
    -String description
    -Boolean completed
  }

  class Card {
    -String number
    -Number limit
  }

  class friend{
    -String icon
    -String name
    -Adventures[] adventures
    -Trophies[] trophies
    -Skills[] skills
    -Hometown hometown
 	}

  class News {
    -String icon
    -String description
  }

  class Skills {
    -String name
    -Number level
  }

  class Travel {
    -String currentLocation
    -Boolean traveling
    -int travels
  }

  class Hometown {
    -String city
    -String state
    -String country
  }

   class Transfer {
     -Date date
     -Double value
     -BasicUser from
     -BasicUser destiny
   }

  User "1" *-- "N" Adventures
  User "1" *-- "N" Friend
  User "1" *-- "1" Account
  User "1" *-- "1" Card
  User "1" *-- "N" News
  User "1" *-- "N" Skills
  User "1" *-- "1" Travel
  User "1" *-- "1" Hometown
  User "1" *-- "N" Transfer
```
