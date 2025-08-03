# Demo DAO JDBC

Demo de implementação do padrão **DAO** utilizando **JDBC** para conexão com um banco de dados relacional (MySQL).

## 🚀 Visão Geral

Este projeto demonstra como implementar operações básicas CRUD em Java usando JDBC e o padrão de projeto DAO, separando lógica de acesso a dados da lógica de negócio.

## 🧩 Funcionalidades

- Consultar todos os registros (e.g., sellers ou departamentos)  
- Consultar registro por ID  
- Filtrar por departamento (quando aplicável)  
- Inserir novo registro  
- Atualizar registro existente  
- Deletar registro  

## 📁 Estrutura do Projeto

```
├── src
│   ├── model
│   │   ├── entities         // classes de domínio (Seller, Department, etc.)
│   │   ├── dao              // interfaces DAO
│   │   └── dao/impl         // implementações JDBC (SellerDaoJDBC, DeptDaoJDBC)
│   ├── db                   // configuração de conexão, fábrica de DAOs
│   └── app                  // classe principal de demonstração (Demo.java ou semelhante)
├── db.properties            // configurações de acesso ao banco
├── database.sql             // script SQL para criar tabelas e dados de exemplo
└── .gitignore
```

## ⚙️ Requisitos

- Java JDK 17+
- MySQL instalado  
- MySQL Connector/J (driver JDBC)

## 🔧 Como Executar

1. Clone o repositório:

```bash
git clone https://github.com/sebastiao25759/demo-dao-jdbc.git
cd demo-dao-jdbc
```

2. Configure o arquivo `db.properties` com suas credenciais MySQL.
3. Execute o script `database.sql` no MySQL para criar o schema e dados iniciais.
4. Abra o projeto em sua IDE Java preferida (IntelliJ, Eclipse, etc.), inclua o driver JDBC no classpath.
5. Execute a classe de demonstração (por exemplo, `Program.java`).

## 🧠 Padrões Utilizados

- **DAO (Data Access Object):** abstrai operações de banco de dados em interfaces específicas.  
- **Factory:** facilita a criação de instâncias DAO com injeção de dependência manual e desacoplamento da lógica de acesso.

## 📌 Tecnologias

- Java  
- JDBC  
- MySQL

## ✔️ Exemplos de Uso

```java
DepartmentDao deptDao = DaoFactory.createDepartmentDao();
SellerDao sellerDao = DaoFactory.createSellerDao();

// Listar todos os departamentos
deptDao.findAll().forEach(System.out::println);

// Inserir novo vendedor
Seller newSeller = new Seller(null, "Maria", "maria@example.com", new Date(), 3000.0, dept);
sellerDao.insert(newSeller);
```

## ✅ Como Contribuir

1. Faça um fork deste repositório.  
2. Crie uma branch para sua funcionalidade:  

```bash
git checkout -b feature/nova-funcionalidade
```

3. Envie suas alterações via pull request.

## 📝 Licença

Distribuído sob a licença **MIT**. Consulte o arquivo `LICENSE` para mais detalhes.
