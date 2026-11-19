# Sistema Farmácia — Banco de Dados
Banco de dados relacional para gerenciar uma farmácia: clientes, funcionários, fornecedores, produtos, estoque por lote, vendas, entregas, receitas médicas e atendimentos farmacêuticos.

## 📋 Sobre o Projeto

Este projeto foi desenvolvido na disciplina de Banco de Dados. O objetivo é modelar e implementar o banco de dados de uma farmácia e praticar os principais comandos SQL de definição (DDL) e manipulação (DML) de dados.

### Entidades do modelo

| Entidade | Descrição | Principais atributos |
|---|---|---|
| **Cliente** | Pessoas que compram ou recebem atendimento na farmácia | Nome, CPF, Telefone, E-mail, Endereço, Cidade, Data de cadastro |
| **Funcionario** | Colaboradores que trabalham no caixa e fazem atendimentos farmacêuticos | Nome, Matrícula, Cargo, Salário, Data de admissão, Ativo |
| **Fornecedor** | Empresas parceiras que abastecem a farmácia | Razão social, CNPJ, Telefone, E-mail, Cidade, Ativo |
| **Produto** | Medicamentos e demais itens vendidos | Nome, Categoria, Fabricante, Princípio ativo, Precisa receita, Preço |
| **Lote** | Unidades físicas de um produto no estoque, usadas no controle de validade | Número do lote, Data de validade, Quantidade disponível, Data de entrada |
| **Venda** | Cada venda registrada | Data da venda, Valor total, Forma de pagamento |
| **Entrega** | Acompanhamento das vendas que precisam ser entregues | Situação do pedido, Endereço de entrega, Taxa de entrega |
| **Receita_medica** | Prescrições exigidas para liberar certos medicamentos | CRM do médico, Nome do médico, Data de emissão, Posologia, Retida |
| **Atendimento** | Serviços farmacêuticos prestados (aferição de pressão, glicemia, orientação) | Data, Horário, Tipo de serviço, Descrição, Valor |

### Relacionamentos

- Um **Produto** tem vários **Lotes**, e cada lote vem de um **Fornecedor**.
- Uma **Venda** pertence a um **Cliente** (pode ficar vazio em venda de balcão) e é feita por um **Funcionario**.
- Uma **Venda** pode ter uma **Entrega** (relação 1:1).
- Uma **Receita_medica** pertence a um **Cliente**, libera um **Produto** e pode ficar ligada a uma **Venda**.
- Um **Atendimento** é feito por um **Funcionario** para um **Cliente**.

### O que o script cobre

**Estrutura**
- Criação e exclusão do banco de dados
- Criação das tabelas com:
  - valores padrão (`DEFAULT`)
  - campos obrigatórios (`NOT NULL`)
  - restrições nomeadas: `PRIMARY KEY` (`pk_`), `FOREIGN KEY` (`fk_`), `UNIQUE` (`uq_`) e `CHECK` (`chk_`)

**Operações feitas em cada tabela**

| Categoria | Operações |
|---|---|
| Manipulação de dados | Inserir tupla com todos os dados · Inserir tupla especificando os atributos · Remover tupla com condição · Atualizar atributo |
| Estrutura | Adicionar e remover coluna · Adicionar e remover índice · Remover tabela |
| Consultas | Todos os atributos · Usando índice (`USE INDEX`) · Com duas condições (`AND`) · Limitando o resultado (`LIMIT`) · Com string no resultado (`CONCAT`) · Com título de coluna (`AS`) · Sem duplicados (`DISTINCT`) · Com cálculo (`SUM`, `AVG`, `DATEDIFF`, operações aritméticas) · Ordenada (`ORDER BY`) · Agrupada (`GROUP BY`) · Filtrada (`HAVING`) |

## 🛠️ Tecnologias Utilizadas

- **[MySQL 8.4](https://www.mysql.com/):** sistema gerenciador de banco de dados (SGBD)
- **[HeidiSQL](https://www.heidisql.com/):** cliente gráfico para criar tabelas, rodar scripts e ver os dados
- **[Aiven](https://aiven.io/):** hospedagem do MySQL na nuvem, compartilhado pelo grupo
- **SQL:** linguagem usada nos scripts DDL e DML

## 📝 Licença

Este projeto é aberto e pode ser utilizado livremente para fins educacionais e pessoais.

## 👨‍💻 Autor

Projeto desenvolvido por:

- [Pedro-Vinicius](https://github.com/PedroVini09)
- [Gabriel-Porto](https://github.com/devgabrielporto07)
- [Sara-Arruda](https://github.com/Sararruda)
- [Luiz-Kaynan](https://github.com/kaynan-CC)
- [Daniel-Mota](https://github.com/danielRMota)
- [Alfredo-Alves](https://github.com/Alfredinkapps)

## 📧 Contato

Para dúvidas, sugestões ou para reportar problemas, entre em contato ou abra uma issue no repositório.

---
