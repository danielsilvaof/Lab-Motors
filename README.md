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

Para utilizar o sistema LAB Motos, clone o repositório e instale as dependências necessárias. Configure as variáveis de ambiente de acordo com o banco de dados e a API utilizada. Após a configuração, execute a aplicação localmente ou via Docker conforme o ambiente desejado. O acesso ao sistema pode ser feito pelo navegador, realizando login ou cadastro de usuários para utilizar todas as funcionalidades de gerenciamento de estoque, clientes e serviços.


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

O sistema LAB Motos foi desenvolvido para resolver problemas críticos de gestão da oficina, que atualmente utiliza planilhas Excel para controle de estoque e não possui cadastro formal de clientes. Esse método manual gera inconsistências nos registros, dificuldades no acompanhamento de peças e materiais e falta de rastreabilidade das movimentações e serviços.

O sistema oferece um módulo completo de controle de estoque, gestão de clientes e acompanhamento de serviços, com funcionalidades que permitem:

* **Registro de entradas e saídas de peças:** cada movimentação é rastreada, garantindo controle preciso do inventário.
* **Gestão de estoque:** monitoramento de quantidades disponíveis, produtos em reserva e níveis críticos, evitando faltas ou excessos.
* **Cadastro e gerenciamento de clientes:** registro completo das informações do cliente, acompanhamento de históricos de atendimento e controle de reservas de serviços.
* **Gerenciamento de serviços:** controle de manutenção das motos em formato Kanban, com status de cada serviço categorizado como "Em Espera", "Em Andamento" ou "Concluído", permitindo acompanhamento visual e atualização em tempo real.
* **Relatórios gerenciais:** geração de dados detalhados sobre estoque, movimentações, clientes e serviços, apoiando decisões estratégicas da oficina.
* **Integração e consistência de dados:** todas as operações centralizadas em banco de dados, eliminando erros de registros manuais.

Com essas funcionalidades, o sistema otimiza processos internos, reduz falhas operacionais, fornece transparência e organização, permitindo à equipe da LAB Motos gerenciar peças, clientes e serviços de forma eficiente, confiável e visualmente intuitiva.

## Histórico de versões

**1.0**

* Implementação inicial do sistema.
* Cadastro de usuários e movimentação de estoque.
* Modelagem do processo de negócio básica.

**2.0**

* Ajustes de interface na Home Page e tela de login/cadastro.
* Correção de links e hrefs.
* Implementação de fluxo de autenticação com feedback visual.

**3.0**

* Adição da Página de Acompanhamento de Serviços.
* Implementação do módulo de Status de Manutenção.
* Relatório detalhado das atividades realizadas.

**4.0**

* Implementação da Página do Administrador (Painel).
* CRUD completo para gerenciamento de peças no estoque.
* Links de gestão adicionais (Clientes cadastrados, Gerenciar widgets).
* Integração com banco de dados (substituindo JSON provisório).

**5.0**

* Atualização de links da API para o deploy.
* Ajustes de interface no Painel e na página de Acompanhamento.
* Adição do Dockerfile para deploy.
* Correções finais de navegação e layout.
