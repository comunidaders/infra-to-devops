# **Curso de Introdução ao SRE e DevOps**

## **Dia 1: Introdução ao SRE e DevOps**

### **Sumário**
- [Sessão Teórica](#sessão-teórica)
  - [Conceitos Básicos de DevOps e SRE](#1-conceitos-básicos-de-devops-e-sre)
  - [Definições e Diferenças entre DevOps e SRE](#2-definições-e-diferenças-entre-devops-e-sre)
  - [Princípios de DevOps](#3-princípios-de-devops)
  - [Princípios de SRE](#4-princípios-de-sre)
  - [Ciclo de Vida DevOps](#5-ciclo-de-vida-devops)
- [Sessão Prática](#sessão-prática)
  - [Configuração de Ambiente](#1-configuração-de-ambiente)
  - [Configuração de Repositório Git para o Curso](#2-configuração-de-repositório-git-para-o-curso)
  - [Atividade](#3-atividade)
- [Material de Apoio](#material-de-apoio)

---

## **Sessão Teórica**

### **1. Conceitos Básicos de DevOps e SRE**

#### **DevOps**
- Integração de desenvolvimento e operações.
- **Objetivo:** Acelerar a entrega de software de alta qualidade.

#### **SRE (Site Reliability Engineering)**
- Desenvolvimento de software focado em confiabilidade.
- **Objetivo:** Garantir que sistemas sejam escaláveis e confiáveis.

### **2. Definições e Diferenças entre DevOps e SRE**

#### **DevOps**
- **Foco:** Cultura de colaboração, automação e integração.
- **Ferramentas:** CI/CD, monitoramento, infraestrutura como código.

#### **SRE**
- **Foco:** Operações como um problema de engenharia.
- **Ferramentas:** SLOs/SLIs, gestão de incidentes, automação de tarefas operacionais.

### **3. Princípios de DevOps**
- **Cultura:** Colaboração entre equipes de desenvolvimento e operações.
- **Automação:** Automação de processos repetitivos.
- **Lean:** Redução de desperdícios e entrega de valor continuamente.
- **Medição:** Medição de processos para otimização contínua.
- **Compartilhamento:** Disseminação de conhecimento e práticas entre equipes.

### **4. Princípios de SRE**
- **Confiabilidade:** Garantir alta disponibilidade e desempenho.
- **Escalabilidade:** Capacidade de escalar operações sem comprometer a confiabilidade.
- **Automação:** Redução do trabalho manual por meio de automação.

### **5. Ciclo de Vida DevOps**
- **Integração Contínua (CI):**
  - **Definição:** Integração frequente de código no repositório central.
  - **Objetivo:** Detectar erros rapidamente.
- **Entrega Contínua (CD):**
  - **Definição:** Preparação de código para liberação automática após a integração.
  - **Objetivo:** Manter código sempre em um estado de prontidão para produção.
- **Implantação Contínua:**
  - **Definição:** Liberação automática de código para produção.
  - **Objetivo:** Reduzir o tempo de entrega de novas funcionalidades.

---

## **Sessão Prática**

### **1. Configuração de Ambiente**

#### **Instalação de Ferramentas Básicas:**
- **Git:** Sistema de controle de versão.
  - **Instalação:** [Instruções de Instalação Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
  - **Comandos Básicos:** `git init`, `git add`, `git commit`, `git push`
- **Docker:** Plataforma para contêineres.
  - **Instalação:** [Instruções de Instalação Docker](https://docs.docker.com/get-docker/)
  - **Comandos Básicos:** `docker run`, `docker build`, `docker-compose`
- **Kubernetes (k3d):** Ferramenta para orquestração de contêineres.
  - **Instalação:** [Instruções de Instalação k3d](https://k3d.io/v5.4.9/)
  - **Comandos Básicos:** `kubectl apply`, `kubectl get pods`, `kubectl describe`

### **2. Configuração de Repositório Git para o Curso**
- **Criação de Repositório:**
  - Escolha a plataforma: [GitHub](https://github.com/), [GitLab](https://gitlab.com/), [Bitbucket](https://bitbucket.org/)
  - **Passos:** Criar um novo repositório, adicionar `.gitignore` e `README.md`
- **Configuração Local:**
  - **Clone:** `git clone [URL do repositório]`
  - **Adicionar Remoto:** `git remote add origin [URL do repositório]`

### **3. Atividade**
- **Criar um Repositório Git e Praticar Commits e Push:**
  - **Passos:**
    1. Criar um repositório localmente: `git init`
    2. Adicionar um arquivo: `echo "# Meu Projeto" > README.md`
    3. Adicionar e commitar: `git add .` e `git commit -m "Inicial commit"`
    4. Configurar remoto e enviar: `git remote add origin [URL do repositório]` e `git push -u origin master`

---

## **Material de Apoio**

### **Slides**
- **[Introdução ao DevOps e SRE](slides/intro-devops-sre.pdf)**: Explicações e diagramas sobre conceitos e diferenças.
- **[Princípios DevOps e SRE](slides/principios-devops-sre.pdf)**: Tópicos CALMS e SLOs/SLIs.
- **[Ciclo de Vida DevOps](slides/ciclo-vida-devops.pdf)**: Diagramas e fluxos de CI/CD.

### **Documentos**
- **[Guia de Instalação de Ferramentas](docs/guia-instalacao-ferramentas.pdf)**: Instruções detalhadas para Git, Docker e Kubernetes.
- **[Guia de Configuração de Repositório](docs/guia-configuracao-repositorio.pdf)**: Passo a passo para configuração e boas práticas.

### **Vídeos**
- **[O que é DevOps?](https://youtu.be/Oy5XetxUvSo)**: Explicações sobre a integração de DevOps.
- **[Introdução ao SRE](https://youtu.be/yuyUJQQudb4)**: Visão geral e diferenças com DevOps.

### **Links Úteis**
- [Documentação Git](https://git-scm.com/doc)
- [Documentação Docker](https://docs.docker.com/)
- [Documentação Kubernetes](https://kubernetes.io/docs/home/)

---

**Dicas:**
- Pratique constantemente e explore comandos novos.
- Promova discussões sobre as diferenças e interseções entre DevOps e SRE.
- Dê feedback contínuo para adaptar as sessões futuras.
