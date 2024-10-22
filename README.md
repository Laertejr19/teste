# Scripts SQL para Criação e População Inicial do Banco de Dados

## Descrição
Este repositório contém scripts SQL para a criação e população inicial do banco de dados necessário para o projeto de gerenciamento de usuários e clientes. As tabelas criadas incluem `tb_agenda`, `tb_clientes` e `tb_usuarios`.

## Estrutura do Banco de Dados

# 1. Tabela tb_agenda
A tabela `tb_agenda` armazena informações sobre os compromissos agendados.

```sql
CREATE TABLE tb_agenda (
  id int NOT NULL AUTO_INCREMENT,
  data date DEFAULT NULL,
  hora time DEFAULT NULL,
  descricao varchar(100) DEFAULT NULL,
  nome_cli varchar(100) DEFAULT NULL,
  PRIMARY KEY (id)
) ENGINE=InnoDB AUTO_INCREMENT=3 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
```
# 2. Tabela tb_clientes
A tabela tb_clientes armazena informações sobre os clientes.
```sql
CREATE TABLE tb_clientes (
  id int NOT NULL AUTO_INCREMENT,
  nome varchar(45) DEFAULT NULL,
  endereco varchar(45) DEFAULT NULL,
  telefone varchar(45) DEFAULT NULL,
  email varchar(45) DEFAULT NULL,
  cpf_cnpj varchar(45) DEFAULT NULL,
  PRIMARY KEY (id)
) ENGINE=InnoDB AUTO_INCREMENT=3 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
```
# 3. Tabela tb_usuarios
A tabela tb_usuarios armazena informações sobre os usuários do sistema.
```sql
CREATE TABLE tb_usuarios (
  id int NOT NULL AUTO_INCREMENT,
  nome varchar(45) DEFAULT NULL,
  email varchar(45) DEFAULT NULL,
  nome_usuario varchar(45) DEFAULT NULL,
  senha varchar(45) DEFAULT NULL,
  PRIMARY KEY (id),
  UNIQUE KEY email_UNIQUE (email),
  UNIQUE KEY nome_usuario_UNIQUE (nome_usuario)
) ENGINE=InnoDB AUTO_INCREMENT=70 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;

População Inicial (Exemplo)
Para popular as tabelas com dados iniciais, utilize os seguintes comandos:
```sql
-- Populando a tabela tb_clientes
INSERT INTO tb_clientes VALUES (1, 'aloha', 'havai', '8898', 'sim', '9988');

-- Populando a tabela tb_usuarios
INSERT INTO tb_usuarios VALUES 
(1, 'Admin', 'Admin', 'Admin', 'Admin'),
(2, 'NomeA', 'EXEMPLO@GMAIL.COM', 'exemploA', '123exemplo'),
(3, 'NomeB', 'ExemploA', 'exemploB', 'exemploB'),
(9, 'NomeC', 'ExemploB', 'ExemploC', 'exemploC'),
(11, 'NomeD', 'ExemploC', 'exemploD', 'exemploD');
```
### Explicação das Seções

- **Título**: Indica o propósito do README.
- **Descrição**: Fornece um resumo do que o repositório contém.
- **Estrutura do Banco de Dados**: Descreve cada tabela que será criada e fornece os scripts SQL correspondentes.
- **População Inicial**: Scripts para popular as tabelas com dados iniciais.
- **Como Executar os Scripts**: Instruções sobre como executar os scripts no MySQL.
- **Considerações Finais**: Dicas e lembretes para garantir que tudo funcione corretamente.

