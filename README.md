# Sistema de Gerenciamento e Controle de Estoque – LAB Motos

`Curso: Análise e Desenvolvimento de Sistemas`  
`Disciplina: Projeto Integrado`  
`Semestre: 2º Semestre`

Este projeto propõe o desenvolvimento de um **sistema de controle de estoque** para a oficina **LAB Motos**, localizada em Santa Luzia/MG e gerida por Cristiano Domingues. Atualmente, o controle é feito de forma manual em planilhas Excel, o que gera inconsistências e ineficiências.  
A solução proposta consiste em um sistema baseado em banco de dados, que permita registrar peças, fornecedores e movimentações, automatizando as entradas e saídas, reduzindo falhas, otimizando a reposição de peças e gerando relatórios gerenciais. O objetivo é aumentar a organização interna, reduzir perdas e apoiar a tomada de decisão.

## Integrantes

* Bruno Silva Moreira
* Daniel Silva de Oliveira
* Davi Oliveira Parma Assunção
* Felippe Salvo de Mendonça
* Gabriel Max Ferreira Rodrigues
* Igor Tiago Ribeiro Matos
* Joao Vitor Carvalho Domingos

## Orientador

* Caroline Rhaian da Silva Jandre,

## Instruções de utilização

Assim que a primeira versão do sistema estiver disponível, deverá complementar com as instruções de utilização.  
Descreva como instalar eventuais dependências e como executar a aplicação.  

# Documentação

1. [Documentação de Contexto](docs/1-Contexto.md)  
2. [Especificação do Projeto](docs/2-Especificação.md)  
3. [Modelagem dos Processos de Negócio](docs/3-Modelagem-Processos-Negócio.md)  
4. [Projeto da solução](docs/4-Projeto-Solucao.md)  
5. [Gerenciamento do Projeto](docs/5-Gerenciamento-Projeto.md)  
6. [Interface do Sistema](docs/6-Interface-Sistema.md)  
7. [Conclusão](docs/7-Conclusão.md)  
8. [Referências](docs/8-Referências.md)  

# Código

* [Código Fonte](src/README.md)

# Apresentação

LAB Motos – Sistema de Gerenciamento e Controle de Estoque

Atualmente, a oficina LAB Motos realiza o controle de estoque manualmente em planilhas Excel, o que gera inconsistências, perda de informações e dificuldades na gestão de peças e materiais. Além disso, não existe um sistema de cadastro de clientes, tornando difícil acompanhar históricos de atendimento e gerenciar reservas ou movimentações de produtos.

Nosso projeto propõe um sistema completo para automatizar o controle de estoque e cadastro de clientes, permitindo:

Registrar entradas e saídas de peças com rastreabilidade;

Controlar quantitativos de produtos disponíveis e reservas;

Cadastrar clientes e gerenciar históricos de atendimento;

Gerar relatórios gerenciais para apoiar decisões da oficina.

O sistema foi desenvolvido como solução direta para os problemas do cliente, otimizando processos internos, reduzindo erros e fornecendo transparência e organização para toda a equipe da LAB Motos.

## Histórico de versões

1.0

Implementação inicial do sistema.
Cadastro de usuários e movimentação de estoque.
Modelagem do processo de negócio básica.

2.0

Ajustes de interface na Home Page e tela de login/cadastro.
Correção de links e hrefs.
Implementação de fluxo de autenticação com feedback visual.

3.0

Adição da Página de Acompanhamento de Serviços.
Implementação do módulo de Status de Manutenção.
Relatório detalhado das atividades realizadas.

4.0

Implementação da Página do Administrador (Painel).
CRUD completo para gerenciamento de peças no estoque.
Links de gestão adicionais (Clientes cadastrados, Gerenciar widgets).
Integração com banco de dados (substituindo JSON provisório).

5.0

Atualização de links da API para o deploy.
Ajustes de interface no Painel e na página de Acompanhamento.
Adição do Dockerfile para deploy.
Correções finais de navegação e layout.
