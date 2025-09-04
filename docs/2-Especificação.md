# Especificações do Projeto

<span style="color:red">Pré-requisitos: <a href="01-Documentação de Contexto.md"> Documentação de Contexto</a></span>

Nesta seção são apresentadas as especificações do sistema de **Gerenciamento e Controle de Estoque da LAB Motos**.  
São descritas as **personas**, as **histórias de usuários**, os **requisitos funcionais e não funcionais** e as **restrições** que irão guiar o desenvolvimento da aplicação.  

A definição desses elementos foi baseada na análise do problema, levantamento de necessidades do proprietário da oficina, estudo de perfis de clientes e boas práticas de levantamento de requisitos.

---

## Personas

### Persona 1 – Cliente Final
- **Nome**: Tiago Nélio  
- **Idade**: 38 anos  
- **Profissão**: Assistente Jurídico  
- **Perfil**: Utiliza a moto diariamente para deslocamentos de trabalho e lazer. Não possui conhecimentos técnicos em mecânica.  
- **Objetivos**: Resolver manutenções de forma rápida e transparente, confiar na oficina e ter clareza sobre preços e prazos.  
- **Dores**: Perder tempo com orçamentos presenciais, insegurança sobre confiabilidade da oficina e falta de clareza nos serviços.  

### Persona 2 – Cliente Profissional
- **Nome**: Cristiano Ronaldo Ribeiro Matos  
- **Idade**: 42 anos  
- **Profissão**: Motofretista  
- **Perfil**: Utiliza a moto como ferramenta de trabalho e depende de manutenções frequentes.  
- **Objetivos**: Ter disponibilidade constante de peças, serviços ágeis e preços competitivos.  
- **Dores**: Perda de rendimento por atrasos na manutenção e indisponibilidade de peças.  

### Persona 3 – Proprietário/Gestor
- **Nome**: Cristiano Domingues  
- **Idade**: 45 anos  
- **Profissão**: Proprietário da LAB Motos  
- **Perfil**: Gerencia a oficina de pequeno porte, com foco em atender clientes de bairro e motofretistas. Atualmente controla o estoque em planilhas manuais.  
- **Objetivos**: Reduzir erros de registro, evitar rupturas de estoque e otimizar a gestão administrativa.  
- **Dores**: Falta de controle efetivo de peças, perdas financeiras e dificuldade para gerar relatórios e prever demandas.  

---

## Histórias de Usuários

|EU COMO... `PERSONA`                  | QUERO/PRECISO ... `FUNCIONALIDADE`              |PARA ... `MOTIVO/VALOR`                  |
|--------------------------------------|------------------------------------------------|-----------------------------------------|
|Cliente Final (Tiago Nélio)           | Saber se a peça está disponível na oficina      | Evitar perda de tempo indo até a oficina|
|Cliente Profissional (Cristiano R.)   | Garantir que o estoque tenha peças de reposição | Não ter sua atividade profissional prejudicada|
|Proprietário (Cristiano Domingues)    | Registrar entradas e saídas de peças            | Controlar de forma organizada o estoque |
|Proprietário (Cristiano Domingues)    | Gerar relatórios mensais                        | Apoiar decisões de compra e reposição   |
|Colaborador da oficina                | Consultar rapidamente a disponibilidade de peças| Prestar atendimento ágil ao cliente     |

---

## Requisitos

### Requisitos Funcionais

|ID     | Descrição do Requisito                                                                 | Prioridade |
|-------|----------------------------------------------------------------------------------------|------------|
|RF-001 | Permitir o cadastro de peças com informações detalhadas (código, descrição, fornecedor)| ALTA       |
|RF-002 | Registrar movimentações de entrada e saída de peças                                    | ALTA       |
|RF-003 | Emitir relatórios de estoque e movimentações                                           | MÉDIA      |
|RF-004 | Permitir a consulta rápida da disponibilidade de peças                                | ALTA       |
|RF-005 | Cadastrar e gerenciar informações de fornecedores                                      | MÉDIA      |

### Requisitos Não Funcionais

|ID     | Descrição do Requisito                                               | Prioridade |
|-------|----------------------------------------------------------------------|------------|
|RNF-001| O sistema deve ser responsivo e funcionar em desktops e dispositivos móveis | MÉDIA      |
|RNF-002| As operações de consulta devem ter tempo de resposta inferior a 3s   | MÉDIA      |
|RNF-003| O sistema deve armazenar os dados em banco relacional                | ALTA       |
|RNF-004| Deve garantir integridade das informações em caso de falhas          | ALTA       |

---

## Restrições

|ID | Restrição                                                        |
|---|------------------------------------------------------------------|
|01 | O projeto deverá ser entregue até o final do semestre letivo     |
|02 | A solução deve ser de baixo custo para atender microempreendedores|
|03 | O desenvolvimento inicial será limitado a um protótipo funcional |

---
