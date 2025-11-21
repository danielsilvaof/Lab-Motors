## 3. Modelagem dos Processos de Negócio

### 3.1. Modelagem da situação atual (Modelagem AS-IS)

Atualmente, a oficina **LAB Motos** realiza o controle de estoque de forma **manual**, utilizando planilhas do Excel.  
Esse processo apresenta diversos gargalos e limitações:

* **Cadastro de peças**: feito manualmente em planilhas, sujeito a erros de digitação e duplicidades.  
* **Entradas e saídas de peças**: registradas apenas quando lembrado, muitas vezes de forma incompleta.  
* **Consulta de disponibilidade**: colaboradores precisam verificar manualmente a planilha, o que gera lentidão no atendimento.  
* **Relatórios gerenciais**: não há geração automática; quando necessários, exigem manipulação manual das planilhas, demandando tempo e aumentando riscos de inconsistência.  
* **Gestão de fornecedores**: não há centralização; informações ficam dispersas, dificultando a análise da performance e prazos de entrega.  

Esse processo manual leva a **inconsistências nos registros, rupturas de estoque, perdas financeiras e atrasos no atendimento ao cliente**.  
Em síntese, o fluxo atual depende fortemente do esforço humano e não garante confiabilidade.  

![asis1](image.png)
![asis2](image-1.png)

1. Cliente solicita peça/manutenção  
2. Colaborador verifica manualmente na planilha  
3. Caso não encontre, consulta diretamente o proprietário  
4. Proprietário decide se compra ou não a peça  
5. Atualização manual da planilha (às vezes feita depois, gerando erros)  

---

### 3.2. Descrição geral da proposta (Modelagem TO-BE)

## 🛑 Análise dos Processos (AS-IS): Problemas Existentes na LAB Motos

O processo atual, altamente manual e baseado em planilhas, gera cinco problemas principais que afetam a eficiência operacional, a confiabilidade dos dados e a satisfação do cliente.

### 1. Inconfiabilidade e Inconsistência do Estoque

Este é o **gargalo central** do processo AS-IS, conforme detalhado no item 3.1.

* **Problema:** O cadastro, as entradas e as saídas de peças são feitos **manualmente em planilhas**. Os registros são feitos "apenas quando lembrado, muitas vezes de forma incompleta".
* **Consequência:** Os dados de estoque são inconsistentes e não refletem a realidade. Isso leva a **rupturas de estoque** (falta de peças necessárias) e **perdas financeiras** devido a erros de registro e inventário incorreto.

### 2. Baixa Produtividade e Lentidão no Atendimento

O processo de verificação de peças e atendimento ao cliente é ineficiente.

* **Problema:** A **Consulta de disponibilidade** é manual. O colaborador precisa abrir e verificar a planilha, o que consome tempo e, se a peça não for encontrada, o fluxo exige a **consulta direta ao proprietário** (conforme o fluxograma AS-IS).
* **Consequência:** Gera **lentidão no atendimento** ao cliente. No fluxo de Atendimento (diagrama AS-IS), o cliente pode ter que esperar **30 minutos** sem garantia de serviço, aumentando a frustração e o risco de **perda do trabalho** ("Ir embora").

### 3. Falta de Governança e Transparência na Decisão de Compra

O processo de reposição de estoque é reativo e desorganizado.

* **Problema:** **Não há relatórios gerenciais automáticos**. As informações de **Gestão de fornecedores** ficam dispersas. O processo de compra se resume à decisão manual do proprietário (se compra ou não a peça) após uma consulta pontual.
* **Consequência:** A compra de peças é feita sem base em dados históricos, volume ou performance de fornecedores. Não há **alertas proativos** para estoque mínimo, resultando em decisões de compra reativas e ineficientes.

### 4. Alto Risco de Erros Humanos

A dependência do esforço e da memória individual é excessiva.

* **Problema:** O processo de **Atualização manual da planilha** é propenso a **erros de digitação e duplicidades**. A atualização "às vezes feita depois" agrava o problema.
* **Consequência:** O processo **depende fortemente do esforço humano**, e qualquer falha no registro manual introduz um erro que pode comprometer todo o fluxo de trabalho e gerar inconsistências financeiras.

### 5. Processo Desconectado

Os diferentes setores da oficina operam com pouca integração sistêmica.

* **Problema:** O Mecânico lista as peças, mas a verificação e o controle de estoque ficam totalmente a cargo do Atendente e da planilha. A comunicação se dá por etapas manuais ("Solicitar peças necessárias", "Enviar peça ao mecânico").
* **Consequência:** O fluxo de informações entre o reparo (**Mecânico**) e a logística (**Estoque/Atendente**) é lento e não automatizado, prolongando o tempo total do serviço.

---

### 3.3. Modelagem dos processos

A solução proposta consiste em um **sistema informatizado de controle de estoque**, centralizado em banco de dados, que permitirá:  

* **Cadastro estruturado** de peças, fornecedores e clientes.  
* **Registro automatizado** de entradas e saídas de estoque.  
* **Consulta rápida** de disponibilidade de peças por qualquer colaborador.  
* **Geração de relatórios gerenciais** (estoque mínimo, movimentações, fornecedores mais utilizados, etc.).  
* **Alertas automáticos** para reposição de peças em risco de ruptura.  

Com isso, o processo será mais ágil, confiável e menos dependente de controles manuais.  
A solução se alinha diretamente à estratégia da oficina LAB Motos de **reduzir perdas, otimizar processos internos e aumentar a satisfação do cliente**.  

![tobe1](image-2.png)
![tobe2](image-3.png)

1. Cliente solicita peça/manutenção  
2. Colaborador consulta disponibilidade no sistema (em tempo real)  
3. Caso não disponível, sistema gera alerta e sugere fornecedor cadastrado  
4. Proprietário realiza pedido de reposição com base nos relatórios do sistema  
5. Entradas e saídas registradas automaticamente, com atualização imediata do estoque 
