
# 6. Interface do Sistema

<span style="color:red">Pré-requisitos: <a href="4-Projeto-Solucao.md"> Projeto da Solução</a></span>

_Visão geral da interação do usuário por meio das telas do sistema. Apresente as principais interfaces da plataforma._

## 6.1. Tela principal do sistema

Descrição da Tela Principal do Sistema

  Na Tela Principal estruturamos toda a navegação inicial do sistema. O cabeçalho contém o logo da LAB Motos, uma área dedicada a anúncios e o menu com links para Home, Serviços, Quem Somos, Contato, além dos botões de Login e Cadastro. Logo abaixo, inserimos um banner funcional com identificação da oficina, lista dos serviços representados por ícones e um botão que redireciona diretamente para a página de contato/abertura de OS. Incluímos também uma seção secundária destinada a imagens ou materiais promocionais e um módulo de newsletter integrado ao fluxo de cadastro. Na área “Quem Somos”, exibimos informações institucionais da empresa acompanhadas por uma galeria de apoio visual. Em seguida, na seção de Contatos, listamos endereço, telefone, e-mail e redes sociais, com um botão que leva ao detalhamento completo. Fechamos a página com um rodapé contendo logo, slogan, direitos autorais e atalhos de navegação, garantindo consistência visual e acesso rápido aos principais canais.

![alt text](<LAB MOTOS - Home Page.jpg>)

## 6.2. Telas do processo 1

  Na seção de login, implementamos um fluxo de autenticação objetivo e padronizado. O usuário insere e-mail e senha em um formulário validado em tempo real, com suporte à funcionalidade “lembrar senha” armazenada via localStorage. Também disponibilizamos o acionamento do fluxo de recuperação de credenciais, que redireciona para a interface de redefinição. Ao enviar o formulário, encaminhamos a requisição à nossa API de autenticação, tratamos os retornos de sucesso ou erro e exibimos notificações através do nosso sistema de feedback. Paralelamente, mantemos um painel visual com a identidade da LAB Motos para reforço de marca. Caso o usuário não possua cadastro, incluímos um atalho direto para a tela de criação de conta. O objetivo dessa seção é garantir um processo de entrada rápido, estável e sem fricção.

![alt text](<LAB MOTOS - Login.jpg>)


  Na área de cadastro, implementamos um formulário estruturado para criação de novas contas, contendo os campos de nome, e-mail, telefone, endereço e senha. Aplicamos validações imediatas para garantir preenchimento obrigatório, formato correto de e-mail e força mínima da senha, além da verificação de correspondência entre senha e confirmação. Ao enviar o formulário, enviamos os dados para a nossa API de autenticação, tratamos respostas de erro (como e-mail já registrado ou formato inválido) e exibimos feedback visual ao usuário. Também adicionamos um botão de retorno para navegação direta ao login. Junto ao formulário, mantemos o painel de identidade visual da LAB Motos, reforçando marca e consistência da interface. O objetivo é oferecer um fluxo de registro eficiente, validado e sem ambiguidades.

![alt text](<LAB MOTOS - Cadastro.jpg>)


## 6.3. Telas do processo 2

Permite ao usuário monitorar o progresso de manutenções e interagir com a oficina.
Cabeçalho: acesso às principais seções do sistema e autenticação de usuário.
Banner de Serviços: exibe os serviços oferecidos com ícones e botão de contato rápido.
Status Serviço: apresenta etapas da manutenção ("Em Espera", "Em Manutenção", "Concluído") com indicadores visuais.
Relatório de Serviços: lista detalhadamente atividades realizadas e histórico técnico.
Contatos: centraliza informações de comunicação (telefone, e-mail, redes sociais) e inscrição em newsletter.
Rodapé: mantém identidade visual e informações institucionais.

Objetivo: fornecer acompanhamento detalhado, transparência das operações e canal direto de comunicação.

![alt text](<LAB MOTOS - Status.jpg>)

_Descrição da tela relativa à atividade 2._

[`Tela da atividade 2`](images/)


