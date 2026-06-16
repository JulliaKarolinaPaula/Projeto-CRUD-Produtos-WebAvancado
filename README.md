# Sistema de Gerenciamento de Produtos

## Sobre o Projeto

Este projeto foi desenvolvido como atividade prática da disciplina de Desenvolvimento Web utilizando PHP, HTML, CSS e MySQL.

O sistema permite o gerenciamento de produtos através das operações básicas de banco de dados (CRUD):

* Cadastro de produtos (Create)
* Listagem de produtos (Read)
* Edição de produtos (Update)
* Exclusão de produtos (Delete)

O objetivo é demonstrar a integração entre interface web e banco de dados utilizando PHP e MySQL.

---

## Tecnologias Utilizadas

* PHP 8+
* HTML5
* CSS3
* MySQL
* PDO (PHP Data Objects)

---

## Estrutura do Projeto

```text
sistema-produtos/
│
├── banco.sql
├── conexao.php
├── index.php
├── cadastrar.php
├── editar.php
├── excluir.php
├── style.css
└── README.md
```

---

## Banco de Dados

### Criação do Banco

```sql
CREATE DATABASE sistema_produtos;

USE sistema_produtos;

CREATE TABLE produtos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    descricao TEXT,
    preco DECIMAL(10,2) NOT NULL
);
```

### Estrutura da Tabela

| Campo     | Tipo          | Descrição            |
| --------- | ------------- | -------------------- |
| id        | INT           | Identificador único  |
| nome      | VARCHAR(100)  | Nome do produto      |
| descricao | TEXT          | Descrição do produto |
| preco     | DECIMAL(10,2) | Preço do produto     |

---

## Funcionalidades

### Cadastro de Produtos

Permite cadastrar novos produtos através de um formulário contendo:

* Nome
* Descrição
* Preço

Os dados são enviados para o banco utilizando comandos INSERT.

---

### Listagem de Produtos

Todos os produtos cadastrados são exibidos em uma tabela contendo:

* ID
* Nome
* Descrição
* Preço
* Ações

---

### Edição de Produtos

Ao clicar no botão "Editar", o sistema:

1. Busca os dados do produto.
2. Preenche automaticamente o formulário.
3. Permite alterar as informações.
4. Atualiza o registro utilizando UPDATE.

---

### Exclusão de Produtos

Ao clicar em "Excluir":

1. É exibida uma confirmação.
2. O registro é removido do banco através do comando DELETE.

---

## Segurança Implementada

O sistema utiliza:

### Prepared Statements

Todas as consultas SQL utilizam PDO com parâmetros preparados.

Exemplo:

```php
$stmt = $pdo->prepare(
    "INSERT INTO produtos(nome, descricao, preco)
     VALUES(:nome, :descricao, :preco)"
);
```

### Validação de Dados

* Campos obrigatórios são verificados.
* Uso de htmlspecialchars() para exibição.
* Tratamento de erros de conexão.

---

## Como Executar

### Requisitos

* PHP 8 ou superior
* MySQL
* Apache
* XAMPP ou WAMP

### Passos

#### 1. Clonar o repositório

```bash
git clone https://github.com/seu-usuario/sistema-produtos.git
```

#### 2. Mover para o diretório do servidor

Exemplo XAMPP:

```text
htdocs/sistema-produtos
```

#### 3. Criar banco de dados

Importe o arquivo:

```text
banco.sql
```

através do phpMyAdmin.

#### 4. Configurar conexão

Editar:

```php
conexao.php
```

informando:

```php
$host = "localhost";
$dbname = "sistema_produtos";
$user = "root";
$password = "";
```

#### 5. Executar

Acessar:

```text
http://localhost/sistema-produtos
```

---

## Operações CRUD Implementadas

| Operação | Arquivo       |
| -------- | ------------- |
| Create   | cadastrar.php |
| Read     | index.php     |
| Update   | editar.php    |
| Delete   | excluir.php   |

---

## Critérios Atendidos

### Estrutura do Banco

* Tabela criada corretamente.
* Chave primária.
* Auto incremento.
* Tipos de dados adequados.

### Insert

* Formulário de cadastro.
* Inserção no banco.

### Update

* Listagem.
* Edição de registros.

### Delete

* Exclusão de registros.

### Interface

* HTML semântico.
* CSS responsivo.
* Navegação simples e intuitiva.

---

## Melhorias Futuras

* Sistema de login.
* Busca de produtos.
* Paginação.
* Upload de imagens.
* API REST.
* Framework Bootstrap.

---

## Autor

Projeto desenvolvido para fins acadêmicos demonstrando operações CRUD utilizando PHP e MySQL.
