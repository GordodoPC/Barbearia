
# Projeto Barbearia

Sistema simples para gerenciamento de uma barbearia com cadastro de clientes, funcionários, serviços e (opcionalmente) agendamentos. Interface gráfica feita com **Java Swing** e persistência com **JPA (Java Persistence API)** usando `EntityManager`.

## 📦 Estrutura do Projeto

```
br/com/barbearia/
├── entity/        # Entidades JPA (Cliente, Funcionario, Servico)
├── repository/    # Repositórios manuais com EntityManager
├── service/       # Lógica de negócio
├── util/          # JPAUtil para gerenciar EntityManager
├── view/          # Telas Swing (interfaces gráficas)
├── menu/          # Classe principal de execução e testes
```

## 🚀 Como executar

1. Importe o projeto em sua IDE (IntelliJ, Eclipse, NetBeans).
2. Certifique-se de ter o banco de dados configurado (ver seção abaixo).
3. Rode a classe:

```
br.com.barbearia.view.TelaPrincipal
```

## 🧑‍💼 Funcionalidades implementadas

- Cadastro de Clientes
- Listagem de Clientes
- Cadastro de Funcionários
- Cadastro de Serviços
- (Preparado para incluir Agendamentos)

## 🗃️ Banco de Dados

### Script SQL (MySQL):

```sql
CREATE DATABASE IF NOT EXISTS barbearia DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci;
USE barbearia;

CREATE TABLE cliente (
    id BIGINT NOT NULL AUTO_INCREMENT,
    nome VARCHAR(100) NOT NULL,
    telefone VARCHAR(20),
    PRIMARY KEY (id)
);

CREATE TABLE funcionario (
    id BIGINT NOT NULL AUTO_INCREMENT,
    nome VARCHAR(100) NOT NULL,
    cargo VARCHAR(50),
    PRIMARY KEY (id)
);

CREATE TABLE servico (
    id BIGINT NOT NULL AUTO_INCREMENT,
    descricao VARCHAR(100),
    preco DOUBLE,
    PRIMARY KEY (id)
);
```

### Configuração esperada no `persistence.xml`:

```xml
<property name="javax.persistence.jdbc.driver" value="com.mysql.cj.jdbc.Driver"/>
<property name="javax.persistence.jdbc.url" value="jdbc:mysql://localhost:3306/barbearia?useSSL=false&amp;serverTimezone=UTC"/>
<property name="javax.persistence.jdbc.user" value="root"/>
<property name="javax.persistence.jdbc.password" value="senha"/>
```

> Substitua `root` e `senha` pelo seu usuário e senha do MySQL.

## 🛠️ Requisitos

- Java 8+
- Maven
- MySQL Server
- Driver JDBC do MySQL

## 📌 Observações

- O projeto não utiliza Spring, apenas JPA puro com persistência manual.
- Você pode expandir a aplicação adicionando controle de agendamentos, login de usuários, relatórios etc.

---

Desenvolvido como projeto acadêmico para estudos de Java Desktop e JPA.
