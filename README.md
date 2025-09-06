# 🎬 Banco de Dados **Filmes**

Este projeto cria e popula um banco de dados relacional chamado **Filmes**, contendo informações sobre **atores, filmes, gêneros e elencos**.  
Além disso, inclui exemplos de consultas SQL úteis para explorar os dados.

# 🚀 Como Usar

- Execute o script para criar o banco Filmes.
- Explore os dados usando as queries fornecidas.
- Expanda criando novas relações (ex: diretores, prêmios, bilheteria).


## 📂 Estrutura do Banco de Dados

### **Atores**
| Campo         | Tipo         | Chave | Descrição                 |
|---------------|-------------|-------|---------------------------|
| Id            | int (PK)    | PK    | Identificador do ator     |
| PrimeiroNome  | varchar(20) |       | Primeiro nome do ator     |
| UltimoNome    | varchar(20) |       | Sobrenome do ator         |
| Genero        | varchar(1)  |       | Gênero (M = Masculino, F = Feminino) |

---

### **Filmes**
| Campo   | Tipo         | Chave | Descrição                  |
|---------|-------------|-------|----------------------------|
| Id      | int (PK)    | PK    | Identificador do filme      |
| Nome    | varchar(50) |       | Nome do filme              |
| Ano     | int         |       | Ano de lançamento          |
| Duracao | int         |       | Duração em minutos         |

---

### **Generos**
| Campo   | Tipo         | Chave | Descrição             |
|---------|-------------|-------|-----------------------|
| Id      | int (PK)    | PK    | Identificador do gênero |
| Genero  | varchar(20) |       | Nome do gênero        |

---

### **FilmesGenero**  
*(Relação N:N entre filmes e gêneros)*  

| Campo    | Tipo      | Chave | Descrição                       |
|----------|----------|-------|---------------------------------|
| Id       | int (PK) | PK    | Identificador da relação        |
| IdGenero | int (FK) | FK    | Referência para Generos.Id      |
| IdFilme  | int (FK) | FK    | Referência para Filmes.Id       |

---

### **ElencoFilme**  
*(Relação N:N entre atores e filmes, com papel)*  

| Campo   | Tipo         | Chave | Descrição                        |
|---------|-------------|-------|----------------------------------|
| Id      | int (PK)    | PK    | Identificador da relação         |
| IdAtor  | int (FK)    | FK    | Referência para Atores.Id        |
| IdFilme | int (FK)    | FK    | Referência para Filmes.Id        |
| Papel   | varchar(30) |       | Papel desempenhado pelo ator     |
