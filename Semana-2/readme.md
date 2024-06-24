# **Curso de Introdução ao SRE e DevOps**

## **Dia 2: Contêineres e Orquestração**

### **Sumário**
- [Sessão Teórica](#sessão-teórica)
  - [Contêineres](#1-contêineres)
    - [O que são contêineres e benefícios](#11-o-que-são-contêineres-e-benefícios)
    - [Docker: Conceitos e componentes](#12-docker-conceitos-e-componentes)
  - [Orquestração de Contêineres](#2-orquestração-de-contêineres)
    - [Introdução ao Kubernetes: Arquitetura e componentes principais](#21-introdução-ao-kubernetes-arquitetura-e-componentes-principais)
- [Sessão Prática](#sessão-prática)
  - [Docker](#1-docker)
    - [Criar e executar um contêiner Docker](#11-criar-e-executar-um-contêiner-docker)
    - [Criar um Dockerfile simples](#12-criar-um-dockerfile-simples)
  - [Kubernetes](#2-kubernetes)
    - [Deploy de um aplicativo simples no Kubernetes (k3d)](#21-deploy-de-um-aplicativo-simples-no-kubernetes-k3d)
- [Atividade](#atividade)
- [Material de Apoio](#material-de-apoio)

---

## **Sessão Teórica**

### **1. Contêineres**

#### **1.1 O que são contêineres e benefícios**
- **Definição:**
  - Contêineres são unidades padronizadas de software que empacotam código e suas dependências, garantindo que o aplicativo seja executado de maneira rápida e confiável em qualquer ambiente.
- **Benefícios:**
  - **Portabilidade:** Executam de maneira consistente em diversos ambientes.
  - **Isolamento:** Isolam aplicativos uns dos outros e do sistema host.
  - **Eficiência:** Menos recursos do que máquinas virtuais tradicionais.
  - **Rapidez:** Iniciam rapidamente e ajudam no desenvolvimento ágil.

#### **1.2 Docker: Conceitos e componentes**
- **Conceitos:**
  - **Imagens:** Modelos de contêineres que incluem tudo necessário para rodar um aplicativo.
  - **Contêineres:** Instâncias de execução de uma imagem.
  - **Dockerfile:** Script para criar imagens Docker.
- **Componentes:**
  - **Docker Engine:** Motor de contêinerização que cria e gerencia contêineres.
  - **Docker Hub:** Registro de imagens público onde os usuários podem compartilhar imagens.

### **2. Orquestração de Contêineres**

#### **2.1 Introdução ao Kubernetes: Arquitetura e componentes principais**
- **Arquitetura:**
  - **Master Node:** Controla o cluster, incluindo o agendamento, gerenciamento e monitoramento.
  - **Worker Nodes:** Executam as aplicações em contêineres.
- **Componentes Principais:**
  - **Pods:** Unidades básicas de execução em Kubernetes, podem conter um ou mais contêineres.
  - **Services:** Definem uma política para acessar Pods.
  - **Deployments:** Gerenciam a criação e a atualização de Pods e ReplicaSets.
  - **ConfigMaps e Secrets:** Gerenciam a configuração e dados sensíveis.

---

## **Sessão Prática**

### **1. Docker**

#### **1.1 Criar e executar um contêiner Docker**
- **Passos:**
  - **Criar uma imagem Docker:** `docker build -t minha-imagem .`
  - **Executar um contêiner:** `docker run -d --name meu-container minha-imagem`
  - **Listar contêineres:** `docker ps`
  - **Acessar um contêiner em execução:** `docker exec -it meu-container /bin/sh`

#### **1.2 Criar um Dockerfile simples**
- **Exemplo:**
  ```Dockerfile
  # Use uma imagem base
  FROM node:14

  # Defina o diretório de trabalho
  WORKDIR /usr/src/app

  # Copie arquivos para o contêiner
  COPY . .

  # Instale as dependências
  RUN npm install

  # Exponha a porta que o aplicativo usará
  EXPOSE 8080

  # Comando para rodar a aplicação
  CMD ["node", "app.js"]
