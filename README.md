<h1 align="center">
  📦 Produto API - Spring Boot
</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Java-22-ED8B00?style=for-the-badge&logo=java&logoColor=white" alt="Java 22"/>
  <img src="https://img.shields.io/badge/Spring_Boot-3.3.5-6DB33F?style=for-the-badge&logo=spring&logoColor=white" alt="Spring Boot"/>
  <img src="https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white" alt="SQLite"/>
  <img src="https://img.shields.io/badge/Maven-C71A36?style=for-the-badge&logo=apachemaven&logoColor=white" alt="Maven"/>
</p>

> **Resumo:** Uma API RESTful projetada para atuar como backend de aplicações Web. Focada no gerenciamento de catálogos e estoques de produtos, oferece respostas rápidas e estrutura de persistência leve.

---

## 🎯 Sobre o Projeto

O **Produto API** foi desenvolvido com foco na simplicidade e eficiência para integração com interfaces web (Front-end). Utilizando o ecossistema Spring, a aplicação expõe endpoints para manipulação de dados de produtos, lidando com regras de negócio, validações de integridade e armazenamento utilizando um banco de dados local **SQLite** — o que facilita rodar e testar o projeto sem a necessidade de infraestrutura pesada de banco de dados.

## 🛠️ Stack Tecnológica

*   **Linguagem:** Java 22
*   **Framework Principal:** Spring Boot 3.3.5
*   **Persistência:** Spring Data JPA + Hibernate
*   **Banco de Dados:** SQLite (com `hibernate-community-dialects`)
*   **Validação:** Spring Boot Validation (`@NotEmpty`, etc.)
*   **Ferramentas:** Maven & Spring Boot DevTools

---

## 🏗️ Estrutura de Dados (Entidade)

O domínio principal da aplicação gira em torno da entidade `Produto`, estruturada da seguinte forma:

| Atributo | Tipo | Descrição e Validações |
| :--- | :--- | :--- |
| `id` | `long` | Identificador único gerado automaticamente (Auto Increment) |
| `nome` | `String` | Nome do produto. **Não pode ser vazio** |
| `quantidade` | `int` | Quantidade de itens disponíveis em estoque |
| `preco` | `double` | Valor financeiro do produto |
| `status` | `String` | Estado atual do produto (ex: ATIVO, INATIVO, ESGOTADO) |

---

## 🚀 Como Executar Localmente

### Pré-requisitos
*   [JDK 22](https://jdk.java.net/22/)
*   [Maven](https://maven.apache.org/)

### Configuração do Banco de Dados (SQLite)
Certifique-se de que o arquivo `src/main/resources/application.properties` contém as configurações de conexão e o dialeto correto para que o JPA consiga criar a tabela:

```properties
spring.datasource.url=jdbc:sqlite:produtos.db
spring.datasource.driver-class-name=org.sqlite.JDBC
spring.jpa.database-platform=org.hibernate.community.dialect.SQLiteDialect
spring.jpa.hibernate.ddl-auto=update
