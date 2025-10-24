## 4. Projeto da Solução

<span style="color:red">Pré-requisitos: <a href="03-Modelagem do Processo de Negocio.md"> Modelagem do Processo de Negocio</a></span>


### 4.2. Protótipos de telas

Com base nas histórias de usuário e requisitos funcionais, foram desenvolvidos protótipos para as principais funcionalidades do sistema:

Telas Principais Implementadas:

![alt text](<LAB MOTOS - Login.jpg>)
![alt text](<LAB MOTOS - Cadastro.jpg>)
![alt text](<LAB MOTOS - Serviços.jpg>)
![alt text](<LAB MOTOS - Painel ADM.jpg>)
![alt text](<LAB MOTOS - Home Page.jpg>)
![alt text](<LAB MOTOS - Status.jpg>)

 

## Diagrama de Classes

O diagrama de classes ilustra graficamente como será a estrutura do software, e como cada uma das classes da sua estrutura estarão interligadas. Essas classes servem de modelo para materializar os objetos que executarão na memória.

As referências abaixo irão auxiliá-lo na geração do artefato “Diagrama de Classes”.

> - [Diagramas de Classes - Documentação da IBM](https://www.ibm.com/docs/pt-br/rational-soft-arch/9.6.1?topic=diagrams-class)
> - [O que é um diagrama de classe UML? | Lucidchart](https://www.lucidchart.com/pages/pt/o-que-e-diagrama-de-classe-uml)

## Modelo ER
O modelo entidade-relacionamento foi desenvolvido contemplando todas as entidades necessárias para os processos de negócio identificados:

Entidades Principais:

Usuario (Clientes, Funcionários, Administradores)

Produto (Peças do estoque)

Fornecedor

Movimentacao (Entradas e saídas de estoque)

OrdemServico

Servico

Agendamento

Relacionamentos Chave:

Usuário → OrdemServico (1:N)

Produto → Movimentacao (1:N)

Fornecedor → Produto (1:N)

OrdemServico → Servico (1:N)



### 4.3. Modelo de dados

O modelo entidade-relacionamento foi desenvolvido contemplando todas as entidades necessárias para os processos de negócio identificados:

Entidades Principais:

Usuario (Clientes, Funcionários, Administradores)

Produto (Peças do estoque)

Fornecedor

Movimentacao (Entradas e saídas de estoque)

OrdemServico

Servico

Agendamento

#### 4.3.1 Modelo ER

O Modelo ER representa através de um diagrama como as entidades (coisas, objetos) se relacionam entre si na aplicação interativa.]

As referências abaixo irão auxiliá-lo na geração do artefato “Modelo ER”.

> - [Como fazer um diagrama entidade relacionamento | Lucidchart](https://www.lucidchart.com/pages/pt/como-fazer-um-diagrama-entidade-relacionamento)

#### 4.3.2 Esquema Relacional

O Esquema Relacional corresponde à representação dos dados em tabelas juntamente com as restrições de integridade e chave primária.
 
As referências abaixo irão auxiliá-lo na geração do artefato “Esquema Relacional”.

> - [Criando um modelo relacional - Documentação da IBM](https://www.ibm.com/docs/pt-br/cognos-analytics/10.2.2?topic=designer-creating-relational-model)

![Exemplo de um modelo relacional](images/modeloRelacional.png "Exemplo de Modelo Relacional.")
---


#### 4.3.3 Modelo Físico

Insira aqui o script de criação das tabelas do banco de dados.

Veja um exemplo:

<code>

 CREATE TABLE IF NOT EXISTS cliente (
  cpf_cnpj        varchar(20) PRIMARY KEY,
  nome            varchar(120) NOT NULL,
  email           varchar(120),
  data_cadastro   timestamp,
  logradouro      varchar(120),
  numero          varchar(10),
  bairro          varchar(60),
  cidade          varchar(60),
  uf              char(2),
  cep             varchar(12)
);
-- Telefones multivalorados do CLIENTE
CREATE TABLE IF NOT EXISTS cliente_telefone (
  cpf_cnpj  varchar(20) NOT NULL REFERENCES cliente(cpf_cnpj) ON UPDATE CASCADE ON DELETE CASCADE,
  telefone  varchar(20) NOT NULL,
  PRIMARY KEY (cpf_cnpj, telefone)
);
-- =====================
-- Tabela: MOTO
-- =====================
CREATE TABLE IF NOT EXISTS moto (
  placa             varchar(10) PRIMARY KEY,
  renavam           varchar(15) UNIQUE,
  marca             varchar(60),
  modelo            varchar(60),
  ano               smallint CHECK (ano BETWEEN 1900 AND 2100),
  cor               varchar(30),
  chassi            varchar(30),
  cilindrada        integer,
  cliente_cpf_cnpj  varchar(20) NOT NULL REFERENCES cliente(cpf_cnpj) ON UPDATE CASCADE
);
CREATE INDEX IF NOT EXISTS idx_moto_cliente ON moto(cliente_cpf_cnpj);
-- =====================
-- Tabela: FUNCIONARIO
-- =====================
CREATE TABLE IF NOT EXISTS funcionario (
  matricula varchar(20) PRIMARY KEY,
  nome      varchar(120) NOT NULL,
  cargo     varchar(80),
  email     varchar(120),
  telefone  varchar(20),
  status    varchar(20)
);
-- =====================
-- Tabela: SERVICO
-- =====================
CREATE TABLE IF NOT EXISTS servico (
  codigo_servico  varchar(20) PRIMARY KEY,
  descricao       varchar(200) NOT NULL,
  tempo_estimado  interval,
  preco_base      numeric(12,2)
);
-- =====================
-- Tabela: AGENDAMENTO
-- =====================
CREATE TABLE IF NOT EXISTS agendamento (
  codigo_agendamento   varchar(20) PRIMARY KEY,
  data_hora            timestamp NOT NULL,
  status               varchar(20),
  observacoes          text,
  cliente_cpf_cnpj     varchar(20) NOT NULL REFERENCES cliente(cpf_cnpj) ON UPDATE CASCADE,
  placa                varchar(10) NOT NULL REFERENCES moto(placa) ON UPDATE CASCADE,
  funcionario_matricula varchar(20) REFERENCES funcionario(matricula) ON UPDATE CASCADE
);
CREATE INDEX IF NOT EXISTS idx_agendamento_cliente ON agendamento(cliente_cpf_cnpj);
CREATE INDEX IF NOT EXISTS idx_agendamento_moto ON agendamento(placa);
CREATE INDEX IF NOT EXISTS idx_agendamento_func ON agendamento(funcionario_matricula);
-- =====================
-- Tabela: ORDEM_SERVICO
-- =====================
CREATE TABLE IF NOT EXISTS ordem_servico (
  numero_os         varchar(20) PRIMARY KEY,
  data_abertura     timestamp NOT NULL,
  data_fechamento   timestamp,
  status            varchar(20),
  quilometragem     integer,
  descricao_problema text,
  cliente_cpf_cnpj  varchar(20) NOT NULL REFERENCES cliente(cpf_cnpj) ON UPDATE CASCADE,
  placa             varchar(10) NOT NULL REFERENCES moto(placa) ON UPDATE CASCADE
);
CREATE INDEX IF NOT EXISTS idx_os_cliente ON ordem_servico(cliente_cpf_cnpj);
CREATE INDEX IF NOT EXISTS idx_os_moto ON ordem_servico(placa);
-- =====================
-- Tabela: DIAGNOSTICO
-- =====================
CREATE TABLE IF NOT EXISTS diagnostico (
  codigo_diag   varchar(20) PRIMARY KEY,
  data_hora     timestamp NOT NULL,
  descricao     text,
  conclusao     text,
  numero_os     varchar(20) NOT NULL REFERENCES ordem_servico(numero_os) ON UPDATE CASCADE ON DELETE CASCADE
);
CREATE INDEX IF NOT EXISTS idx_diag_os ON diagnostico(numero_os);
-- =====================
-- N:M ORDEM_SERVICO <-> SERVICO
-- =====================
CREATE TABLE IF NOT EXISTS ordem_servico_servico (
  numero_os       varchar(20) NOT NULL REFERENCES ordem_servico(numero_os) ON UPDATE CASCADE ON DELETE CASCADE,
  codigo_servico  varchar(20) NOT NULL REFERENCES servico(codigo_servico) ON UPDATE CASCADE,
  quantidade      integer NOT NULL DEFAULT 1,
  valor_unitario  numeric(12,2),
  desconto        numeric(12,2) DEFAULT 0,
  PRIMARY KEY (numero_os, codigo_servico)
);
-- =====================
-- Tabela: ORCAMENTO
-- =====================
CREATE TABLE IF NOT EXISTS orcamento (
  numero_orcamento   varchar(20) PRIMARY KEY,
  data_emissao       date NOT NULL,
  validade_ate       date,
  status             varchar(20),
  valor_estimado     numeric(12,2),
  cliente_cpf_cnpj   varchar(20) NOT NULL REFERENCES cliente(cpf_cnpj) ON UPDATE CASCADE,
  placa              varchar(10) NOT NULL REFERENCES moto(placa) ON UPDATE CASCADE,
  numero_os          varchar(20) REFERENCES ordem_servico(numero_os) ON UPDATE CASCADE
);
CREATE INDEX IF NOT EXISTS idx_orc_cliente ON orcamento(cliente_cpf_cnpj);
CREATE INDEX IF NOT EXISTS idx_orc_moto ON orcamento(placa);
CREATE INDEX IF NOT EXISTS idx_orc_os ON orcamento(numero_os);
-- =====================
-- N:M ORCAMENTO <-> SERVICO
-- =====================
CREATE TABLE IF NOT EXISTS orcamento_servico (
  numero_orcamento  varchar(20) NOT NULL REFERENCES orcamento(numero_orcamento) ON UPDATE CASCADE ON DELETE CASCADE,
  codigo_servico    varchar(20) NOT NULL REFERENCES servico(codigo_servico) ON UPDATE CASCADE,
  quantidade        integer NOT NULL DEFAULT 1,
  valor_unitario    numeric(12,2),
  desconto          numeric(12,2) DEFAULT 0,
  PRIMARY KEY (numero_orcamento, codigo_servico)
);
-- =====================
-- Tabela: PECA
-- =====================
CREATE TABLE IF NOT EXISTS peca (
  sku        varchar(30) PRIMARY KEY,
  descricao  varchar(200) NOT NULL,
  unidade    varchar(10),
  situacao   varchar(20)
);
-- =====================
-- N:M ORCAMENTO <-> PECA
-- =====================
CREATE TABLE IF NOT EXISTS orcamento_peca (
  numero_orcamento  varchar(20) NOT NULL REFERENCES orcamento(numero_orcamento) ON UPDATE CASCADE ON DELETE CASCADE,
  sku               varchar(30) NOT NULL REFERENCES peca(sku) ON UPDATE CASCADE,
  quantidade        numeric(12,3) NOT NULL,
  valor_unitario    numeric(12,2),
  desconto          numeric(12,2) DEFAULT 0,
  PRIMARY KEY (numero_orcamento, sku)
);
-- =====================
-- Tabela: REQUISICAO_PECAS
-- =====================
CREATE TABLE IF NOT EXISTS requisicao_pecas (
  codigo_req     varchar(20) PRIMARY KEY,
  data_solicitacao timestamp NOT NULL,
  status         varchar(20),
  numero_os      varchar(20) NOT NULL REFERENCES ordem_servico(numero_os) ON UPDATE CASCADE
);
CREATE INDEX IF NOT EXISTS idx_req_os ON requisicao_pecas(numero_os);
-- =====================
-- N:M REQUISICAO_PECAS <-> PECA
-- =====================
CREATE TABLE IF NOT EXISTS requisicao_pecas_item (
  codigo_req  varchar(20) NOT NULL REFERENCES requisicao_pecas(codigo_req) ON UPDATE CASCADE ON DELETE CASCADE,
  sku         varchar(30) NOT NULL REFERENCES peca(sku) ON UPDATE CASCADE,
  quantidade  numeric(12,3) NOT NULL,
  PRIMARY KEY (codigo_req, sku)
);
-- =====================
-- Tabela: MOVIMENTO_ESTOQUE
-- =====================
CREATE TABLE IF NOT EXISTS movimento_estoque (
  numero_mov   varchar(20) PRIMARY KEY,
  data_hora    timestamp NOT NULL,
  tipo         varchar(10) NOT NULL,     -- ENTRADA/SAIDA/AJUSTE/etc.
  quantidade   numeric(12,3) NOT NULL,
  origem_tipo  varchar(30) NOT NULL,     -- 'PEDIDO_COMPRA', 'RECEBIMENTO', 'ORDEM_SERVICO', 'AJUSTE', ...
  origem_id    varchar(30),
  observacao   text,
  sku          varchar(30) NOT NULL REFERENCES peca(sku) ON UPDATE CASCADE
);
CREATE INDEX IF NOT EXISTS idx_mov_peca_data ON movimento_estoque (sku, data_hora);
CREATE INDEX IF NOT EXISTS idx_mov_origem ON movimento_estoque (origem_tipo, origem_id);
-- =====================
-- Tabela: FORNECEDOR
-- =====================
CREATE TABLE IF NOT EXISTS fornecedor (
  cnpj          varchar(20) PRIMARY KEY,
  razao_social  varchar(160) NOT NULL,
  email         varchar(120),
  telefone      varchar(20),
  logradouro    varchar(120),
  numero        varchar(10),
  bairro        varchar(60),
  cidade        varchar(60),
  uf            char(2),
  cep           varchar(12)
);
-- =====================
-- Tabela: PEDIDO_COMPRA
-- =====================
CREATE TABLE IF NOT EXISTS pedido_compra (
  numero_pedido  varchar(20) PRIMARY KEY,
  data_emissao   timestamp NOT NULL,
  status         varchar(20),
  valor_total    numeric(14,2),
  cnpj           varchar(20) NOT NULL REFERENCES fornecedor(cnpj) ON UPDATE CASCADE
);
CREATE INDEX IF NOT EXISTS idx_pedido_fornecedor ON pedido_compra(cnpj);
-- =====================
-- N:M PEDIDO_COMPRA <-> PECA
-- =====================
CREATE TABLE IF NOT EXISTS pedido_compra_item (
  numero_pedido  varchar(20) NOT NULL REFERENCES pedido_compra(numero_pedido) ON UPDATE CASCADE ON DELETE CASCADE,
  sku            varchar(30) NOT NULL REFERENCES peca(sku) ON UPDATE CASCADE,
  quantidade     numeric(12,3) NOT NULL,
  valor_unitario numeric(12,2) NOT NULL,
  desconto       numeric(12,2) DEFAULT 0,
  PRIMARY KEY (numero_pedido, sku)
);
-- =====================
-- Tabela: RECEBIMENTO
-- =====================
CREATE TABLE IF NOT EXISTS recebimento (
  numero_receb      varchar(20) PRIMARY KEY,
  numero_nfe        varchar(60),
  data_recebimento  timestamp NOT NULL,
  status            varchar(20),
  frete             numeric(12,2) DEFAULT 0,
  desconto          numeric(12,2) DEFAULT 0,
  numero_pedido     varchar(20) NOT NULL REFERENCES pedido_compra(numero_pedido) ON UPDATE CASCADE
);
CREATE INDEX IF NOT EXISTS idx_receb_pedido ON recebimento(numero_pedido);
-- =====================
-- N:M RECEBIMENTO <-> PECA
-- =====================
CREATE TABLE IF NOT EXISTS recebimento_item (
  numero_receb  varchar(20) NOT NULL REFERENCES recebimento(numero_receb) ON UPDATE CASCADE ON DELETE CASCADE,
  sku           varchar(30) NOT NULL REFERENCES peca(sku) ON UPDATE CASCADE,
  quantidade    numeric(12,3) NOT NULL,
  valor_unitario numeric(12,2),
  PRIMARY KEY (numero_receb, sku)
);
-- =====================
-- View: saldo de estoque por peça (opcional)
-- =====================
CREATE OR REPLACE VIEW vw_saldo_estoque AS
SELECT
  p.sku,
  COALESCE(SUM(CASE WHEN LOWER(m.tipo) IN ('entrada','compra','ajuste+','devolucao') THEN m.quantidade
                    WHEN LOWER(m.tipo) IN ('saida','consumo','ajuste-') THEN -m.quantidade
                    ELSE 0 END), 0) AS saldo
FROM peca p
LEFT JOIN movimento_estoque m ON m.sku = p.sku
GROUP BY p.sku;
</code>

Este script deverá ser incluído em um arquivo .sql na pasta src\bd.




### 4.4. Tecnologias

_Descreva qual(is) tecnologias você vai usar para resolver o seu problema, ou seja, implementar a sua solução. Liste todas as tecnologias envolvidas, linguagens a serem utilizadas, serviços web, frameworks, bibliotecas, IDEs de desenvolvimento, e ferramentas._

Apresente também uma figura explicando como as tecnologias estão relacionadas ou como uma interação do usuário com o sistema vai ser conduzida, por onde ela passa até retornar uma resposta ao usuário.


| **Dimensão**   | **Tecnologia**  |
| ---            | ---             |
| SGBD           | SQL Server           |
| Front end      | HTML+CSS+JS/ React     |
| Back end       | C# |
| Deploy         | Github/ Azure    |


