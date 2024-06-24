# **Curso de Introdução ao SRE e DevOps**

## **Dia 7: Cultura DevOps e Melhoria Contínua**

### **Sumário**
- [Sessão Teórica](#sessão-teórica)
  - [Cultura DevOps](#1-cultura-devops)
    - [Colaboração entre equipes](#11-colaboração-entre-equipes)
    - [Feedback contínuo e melhoria contínua](#12-feedback-contínuo-e-melhoria-contínua)
  - [SRE Práticas](#2-sre-práticas)
    - [SLOs, SLIs, e SLAs](#21-slos-slis-e-slas)
    - [Redução de Toil](#22-redução-de-toil)
- [Sessão Prática](#sessão-prática)
  - [Melhoria Contínua](#1-melhoria-contínua)
    - [Revisão de pipelines e infraestrutura configurada ao longo da semana](#11-revisão-de-pipelines-e-infraestrutura-configurada-ao-longo-da-semana)
    - [Implementação de melhorias e otimizações](#12-implementação-de-melhorias-e-otimizações)
- [Atividade](#atividade)
- [Material de Apoio](#material-de-apoio)

---

## **Sessão Teórica**

### **1. Cultura DevOps**

#### **1.1 Colaboração entre equipes**
- **Definição:**
  - A cultura DevOps promove a colaboração entre as equipes de desenvolvimento, operações e outras partes interessadas para alcançar objetivos comuns.
- **Objetivos:**
  - **Comunicação:** Facilitar a comunicação clara e frequente entre as equipes.
  - **Integração:** Integrar processos e ferramentas para eliminar silos.
  - **Responsabilidade Compartilhada:** Distribuir a responsabilidade pelo sucesso do projeto entre todas as equipes.
- **Práticas:**
  - **Daily Stand-ups:** Reuniões diárias para sincronizar o progresso e discutir obstáculos.
  - **Retrospectivas:** Revisões regulares para discutir o que funcionou bem e o que pode ser melhorado.

#### **1.2 Feedback contínuo e melhoria contínua**
- **Definição:**
  - O feedback contínuo envolve coletar e agir sobre informações de retorno de maneira constante para melhorar processos e produtos.
- **Objetivos:**
  - **Aprendizagem:** Facilitar a aprendizagem rápida e a adaptação.
  - **Otimização:** Identificar áreas para otimização contínua.
- **Práticas:**
  - **Monitoramento:** Uso de ferramentas de monitoramento para obter feedback em tempo real.
  - **Automação de Testes:** Implementação de testes automatizados para fornecer feedback rápido sobre a integridade do código.
  - **KPIs e Métricas:** Definição e monitoramento de KPIs para avaliar o desempenho.

### **2. SRE Práticas**

#### **2.1 SLOs, SLIs, e SLAs**
- **Definições:**
  - **SLO (Service Level Objective):** Objetivos específicos que definem a expectativa de desempenho de um serviço.
  - **SLI (Service Level Indicator):** Métricas que indicam o desempenho real de um serviço em relação aos SLOs.
  - **SLA (Service Level Agreement):** Acordo formal que define os níveis de serviço esperados entre um provedor de serviço e um cliente.
- **Objetivos:**
  - **Medir e Gerenciar:** Utilizar SLOs e SLIs para medir e gerenciar o desempenho de serviços.
  - **Confiabilidade:** Garantir a confiabilidade do serviço com base nos SLAs acordados.
- **Práticas:**
  - **Definição de SLOs:** Estabelecer metas claras e mensuráveis.
  - **Monitoramento de SLIs:** Implementar monitoramento para SLIs relevantes.
  - **Revisão de SLAs:** Revisar e atualizar SLAs regularmente para refletir as necessidades atuais.

#### **2.2 Redução de Toil**
- **Definição:**
  - Toil refere-se ao trabalho repetitivo, manual e de baixo valor que não escalona conforme a infraestrutura cresce.
- **Objetivos:**
  - **Automatização:** Reduzir toil através da automação de tarefas repetitivas.
  - **Eficiência:** Melhorar a eficiência das operações.
- **Práticas:**
  - **Automatização de Tarefas:** Utilizar scripts e ferramentas para automatizar processos manuais.
  - **Documentação:** Documentar procedimentos para reduzir toil em tarefas de suporte e operações.

---

## **Sessão Prática**

### **1. Melhoria Contínua**

#### **1.1 Revisão de pipelines e infraestrutura configurada ao longo da semana**
- **Passos:**
  1. **Análise de Pipelines Existentes:**
     - Revise os pipelines CI/CD criados ao longo da semana.
     - Identifique áreas que podem ser otimizadas, como tempos de build, execução de testes, ou deploys.
  2. **Revisão da Infraestrutura:**
     - Revise a infraestrutura provisionada usando Terraform.
     - Identifique oportunidades para simplificação, automação, ou melhoria da segurança.

#### **1.2 Implementação de melhorias e otimizações**
- **Passos:**
  1. **Identificar Melhorias:**
     - Liste possíveis melhorias com base na revisão.
     - Exemplo: Reduzir o tempo de execução do pipeline, adicionar mais testes automatizados, otimizar configurações Terraform.
  2. **Implementar Melhorias:**
     - Aplique as melhorias identificadas.
     - Exemplo: Modificar o pipeline YAML para incluir novos testes, atualizar scripts Terraform para melhorar o desempenho.
  3. **Testar e Validar:**
     - Teste as melhorias implementadas.
     - Verifique se os pipelines e a infraestrutura funcionam conforme esperado.

---

## **Atividade**
- **Identificar e implementar uma melhoria em um pipeline ou na infraestrutura existente:**
  - **Passos:**
    1. **Revisar Pipelines/Infraestrutura:**
       - Examine os pipelines CI/CD e a infraestrutura configurada durante o curso.
    2. **Identificar Melhorias:**
       - Proponha uma melhoria específica que pode ser implementada.
    3. **Implementar e Testar:**
       - Aplique a melhoria e valide se ela alcança os resultados desejados.

---

## **Material de Apoio**

### **Slides**
- **[Cultura DevOps](slides/cultura-devops.pdf)**: Importância da colaboração e feedback contínuo.
- **[Práticas SRE](slides/praticas-sre.pdf)**: SLOs, SLIs, SLAs e redução de toil.

### **Documentos**
- **[Guia de SLOs, SLIs e SLAs](docs/guia-slos-slis-slas.pdf)**: Instruções detalhadas sobre como definir e monitorar SLOs, SLIs, e SLAs.
- **[Guia de Melhoria Contínua](docs/guia-melhoria-continua.pdf)**: Estratégias para a implementação de melhoria contínua em DevOps.

### **Vídeos**
- **[O que é Cultura DevOps?](https://youtu.be/K53qkRUuWMA)**
- **[Práticas SRE e Redução de Toil](https://youtu.be/2njpAonx0fE)**

### **Links Úteis**
- [Documentação SRE](https://sre.google/sre-book/)
- [Documentação DevOps](https://www.atlassian.com/devops)

---

**Dicas:**
- Realize revisões periódicas dos pipelines e da infraestrutura para identificar melhorias contínuas.
- Envolva todas as partes interessadas na identificação de áreas de melhoria.
- Utilize feedback e métricas para direcionar a otimização de processos.
