# Plano de Aulas: Transição para SRE/DevOps

## Objetivo

Este plano de aulas tem como objetivo fornecer uma introdução prática e teórica aos conceitos, ferramentas e práticas essenciais de SRE e DevOps para profissionais de infraestrutura que desejam migrar para essas áreas.

## Formato das Aulas

- **Duração Diária:** 2-3 horas
- **Componentes:** 
  - Teoria (1 hora)
  - Prática (1-2 horas)
  - Q&A (30 minutos)

---

## Dia 1: Introdução ao SRE e DevOps

### Sessão Teórica
- **Conceitos Básicos de DevOps e SRE**
  - Definições e diferenças entre DevOps e SRE
  - Princípios de DevOps: Cultura, Automação, Lean, Medição, Compartilhamento (CALMS)
  - Princípios de SRE: Confiabilidade, Escalabilidade, Automação
- **Ciclo de Vida DevOps**
  - Integração Contínua (CI), Entrega Contínua (CD), Implantação Contínua

### Sessão Prática
- **Configuração de Ambiente**
  - Instalação de ferramentas básicas: Git, Docker, Kubernetes (minikube ou Kind)
  - Configuração de repositório Git para o curso

### Atividade
- Criar um repositório Git e praticar commits e push.

---

## Dia 2: Contêineres e Orquestração

### Sessão Teórica
- **Contêineres**
  - O que são contêineres e benefícios
  - Docker: Conceitos e componentes
- **Orquestração de Contêineres**
  - Introdução ao Kubernetes: Arquitetura e componentes principais

### Sessão Prática
- **Docker**
  - Criar e executar um contêiner Docker
  - Criar um Dockerfile simples
- **Kubernetes**
  - Deploy de um aplicativo simples no Kubernetes (usando minikube ou Kind)

### Atividade
- Criar um Dockerfile e executar uma aplicação em Kubernetes.

---

## Dia 3: Integração Contínua (CI)

### Sessão Teórica
- **CI/CD**
  - Conceitos de Integração Contínua
  - Ferramentas de CI: Jenkins, GitHub Actions, Azure Pipelines

### Sessão Prática
- **Pipeline CI**
  - Configurar um pipeline simples de CI (usando GitHub Actions ou Jenkins)
  - Testes automatizados em CI

### Atividade
- Configurar um pipeline CI para um projeto básico.

---

## Dia 4: Entrega e Implantação Contínua (CD)

### Sessão Teórica
- **CD**
  - Conceitos de Entrega Contínua e Implantação Contínua
  - Estratégias de Deploy: Blue-Green, Canary

### Sessão Prática
- **Pipeline CD**
  - Criar e configurar um pipeline de CD para deploy automatizado em Kubernetes

### Atividade
- Configurar um pipeline CD para implantar uma aplicação no Kubernetes.

---

## Dia 5: Monitoramento e Observabilidade

### Sessão Teórica
- **Monitoramento e Observabilidade**
  - Conceitos de Monitoramento e Observabilidade
  - Ferramentas: Prometheus, Grafana, Loki

### Sessão Prática
- **Configuração de Monitoramento**
  - Implementar Prometheus e Grafana em um cluster Kubernetes
  - Configurar alertas básicos

### Atividade
- Configurar dashboards no Grafana e alertas no Prometheus.

---

## Dia 6: Segurança e Automação de Infraestrutura

### Sessão Teórica
- **Segurança em DevOps**
  - Práticas de DevSecOps
  - Ferramentas de Segurança: Scan de Vulnerabilidades, RBAC

### Sessão Prática
- **Infraestrutura como Código (IaC)**
  - Introdução ao Terraform
  - Criar e aplicar um plano Terraform para provisionar recursos

### Atividade
- Criar um script Terraform para provisionar uma VM ou bucket de armazenamento.

---

## Dia 7: Cultura DevOps e Melhoria Contínua

### Sessão Teórica
- **Cultura DevOps**
  - Colaboração entre equipes
  - Feedback contínuo e melhoria contínua
- **SRE Práticas**
  - SLOs, SLIs, e SLAs
  - Redução de Toil

### Sessão Prática
- **Melhoria Contínua**
  - Revisão de pipelines e infraestrutura configurada ao longo da semana
  - Implementação de melhorias e otimizações

### Atividade
- Identificar e implementar uma melhoria em um pipeline ou na infraestrutura existente.

---

## Recursos Recomendados

- **Livros:**
  - "The Phoenix Project" - Gene Kim, Kevin Behr, George Spafford
  - "The DevOps Handbook" - Gene Kim, Patrick Debois, John Willis, Jez Humble
  - "Site Reliability Engineering" - Niall Richard Murphy, Betsy Beyer, Chris Jones, Jennifer Petoff

- **Cursos Online:**
  - **Udemy:** Cursos sobre Docker, Kubernetes, CI/CD
  - **Coursera:** Especializações em DevOps e SRE
  - **Pluralsight:** Vídeos sobre práticas de DevOps

- **Blogs e Artigos:**
  - **DevOps.com**
  - **Google Cloud SRE Articles**
  - **Medium DevOps Stories**

---

## Dicas Adicionais

- **Pratique Regularmente:** A prática constante é essencial para a assimilação de novos conceitos.
- **Participe da Comunidade:** Envolva-se em comunidades de DevOps e SRE para troca de conhecimentos.
- **Experimente Ferramentas:** Não tenha medo de experimentar novas ferramentas e tecnologias.

---

Boa jornada na transição para SRE/DevOps! 🚀
