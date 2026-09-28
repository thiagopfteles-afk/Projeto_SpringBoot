Foi mal! Esqueci de colocar dentro do bloco de código para você conseguir copiar a formatação pura.

Aqui está o código cru do Markdown para você só copiar e colar no seu `README.md`:

```markdown
<h1 align="center">
  📦 Produto API - Spring Boot & Front-end de Consumo
</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Java-22-ED8B00?style=for-the-badge&logo=java&logoColor=white" alt="Java 22"/>
  <img src="https://img.shields.io/badge/Spring_Boot-3.3.5-6DB33F?style=for-the-badge&logo=spring&logoColor=white" alt="Spring Boot"/>
  <img src="https://img.shields.io/badge/Maven-C71A36?style=for-the-badge&logo=apachemaven&logoColor=white" alt="Maven"/>
  <img src="https://img.shields.io/badge/Hibernate-59666C?style=for-the-badge&logo=Hibernate&logoColor=white" alt="Hibernate"/>
  <img src="https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white" alt="SQLite"/>
  <br>
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5"/>
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3"/>
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JavaScript"/>
</p>

> **Resumo:** Uma solução completa contendo uma API RESTful projetada no backend para atuar no gerenciamento de catálogos e estoques de produtos, e uma interface web interativa no frontend para testagem de consumo e exibição dos dados.

---

## 🎯 Sobre o Projeto

O **Produto API** evoluiu de uma simples API para uma aplicação com integração direta a uma interface de usuário. Desenvolvido com foco na simplicidade e eficiência, o ecossistema Spring expõe endpoints robustos para manipulação de dados de produtos, lidando com regras de negócio e validações de integridade.

O armazenamento é gerenciado pelo poderoso ORM **Hibernate**, mapeando os objetos Java para um banco de dados relacional leve e local em **SQLite**. Isso elimina a necessidade de configurações complexas de infraestrutura durante o desenvolvimento.

Para fechar o ciclo da aplicação, o projeto conta agora com uma página Web dedicada (desenvolvida com **HTML**, **CSS** e **JavaScript** puro). Esta página utiliza a *Fetch API* do JavaScript para realizar requisições assíncronas ao backend, preenchendo as tabelas de produtos dinamicamente e demonstrando o consumo real da API.

---

## 🛠️ Stack Tecnológica

### Back-end
*   **Linguagem:** Java 22
*   **Framework:** Spring Boot 3.3.5
*   **Gerenciador de Dependências:** Maven
*   **Persistência (ORM):** Spring Data JPA + Hibernate
*   **Banco de Dados:** SQLite (via `hibernate-community-dialects`)
*   **Validação:** Spring Boot Validation (`@NotEmpty`, etc.)

### Front-end
*   **Estruturação:** HTML5 Semântico
*   **Estilização:** CSS3
*   **Interatividade e Integração:** JavaScript (ES6+ / Fetch API)

---

## 🏗️ Estrutura de Dados (Entidade Produto)

O domínio principal do banco de dados gira em torno da entidade `Produto`, estruturada e validada da seguinte forma:

| Atributo | Tipo | Descrição e Regras |
| :--- | :--- | :--- |
| `id` | `long` | Identificador único gerado automaticamente (Auto Increment) |
| `nome` | `String` | Nome descritivo do produto. **(Não pode ser vazio ou nulo)** |
| `quantidade` | `int` | Quantidade de itens disponíveis em estoque. |
| `preco` | `double` | Valor financeiro de venda do produto. |
| `status` | `String` | Estado atual do item (Ex: `ATIVO`, `INATIVO`, `ESGOTADO`). |

---

## 🚀 Como Executar Localmente

### Pré-requisitos
1.  [JDK 22](https://jdk.java.net/22/) instalado.
2.  [Maven](https://maven.apache.org/) configurado nas variáveis de ambiente.
3.  Um navegador web atualizado (Chrome, Firefox, Edge).

### 1. Configurando e Rodando a API (Back-end)

Certifique-se de que o arquivo `src/main/resources/application.properties` contém as configurações corretas para a criação automática da tabela pelo Hibernate no SQLite:

```properties
# Conexão com o banco local
spring.datasource.url=jdbc:sqlite:produtos.db
spring.datasource.driver-class-name=org.sqlite.JDBC

# Configurações do Hibernate / JPA
spring.jpa.database-platform=org.hibernate.community.dialect.SQLiteDialect
spring.jpa.hibernate.ddl-auto=update

```

> **Aviso de CORS:** Como o frontend em HTML/JS fará requisições locais (ex: `http://localhost:8000`), certifique-se de que a sua classe Controller no Spring Boot possui a anotação `@CrossOrigin(origins = "*")` para permitir que o navegador acesse os dados sem bloqueios de segurança.

Para iniciar o servidor, abra o terminal na raiz do projeto e execute:

```bash
mvn spring-boot:run

```

A API estará disponível, por padrão, na porta configurada (ex: `http://localhost:8000`).

### 2. Rodando a Interface (Front-end)

Como o front-end foi construído com tecnologias web padrão (HTML/CSS/JS), não é necessário compilar nada.

1. Navegue até a pasta onde o arquivo `index.html` (ou a sua página principal) está salvo.
2. Dê um duplo clique no arquivo para abri-lo no seu navegador.
3. A página utilizará o JavaScript para buscar automaticamente a lista de produtos no seu servidor Spring Boot e renderizar a tabela na tela.

```

```
