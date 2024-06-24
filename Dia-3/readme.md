# **Curso de Introdução ao SRE e DevOps**

## **Dia 3: Integração Contínua (CI)**

### **Sumário**
- [Sessão Teórica](#sessão-teórica)
  - [CI/CD](#1-cicd)
    - [Conceitos de Integração Contínua](#11-conceitos-de-integração-contínua)
    - [Ferramentas de CI](#12-ferramentas-de-ci)
- [Sessão Prática](#sessão-prática)
  - [Pipeline CI](#1-pipeline-ci)
    - [Configurar um pipeline simples de CI](#11-configurar-um-pipeline-simples-de-ci)
    - [Testes automatizados em CI](#12-testes-automatizados-em-ci)
- [Atividade](#atividade)
- [Material de Apoio](#material-de-apoio)

---

## **Sessão Teórica**

### **1. CI/CD**

#### **1.1 Conceitos de Integração Contínua**
- **Definição:**
  - Integração Contínua (CI) é a prática de integrar código em um repositório compartilhado várias vezes ao dia.
- **Objetivos:**
  - **Detecção precoce de falhas:** Ajudar a identificar problemas de integração rapidamente.
  - **Automação:** Automatizar a compilação e teste do código.
  - **Qualidade:** Melhorar a qualidade do software através de feedback contínuo.

#### **1.2 Ferramentas de CI**
- **Jenkins:**
  - Plataforma de automação de código aberto para CI/CD.
  - **Recursos:** Plugins extensíveis, pipelines de script, interface web.
- **GitHub Actions:**
  - Plataforma de automação integrada ao GitHub.
  - **Recursos:** Workflows baseados em eventos, suporte a contêineres, YAML para configuração.
- **Azure Pipelines:**
  - Serviço de CI/CD da Azure DevOps.
  - **Recursos:** Pipelines YAML, integração com Azure e outras ferramentas DevOps.

---

## **Sessão Prática**

### **1. Pipeline CI**

#### **1.1 Configurar um pipeline simples de CI**
- **Ferramentas Utilizadas:** GitHub Actions ou Jenkins (opcionalmente Azure Pipelines na atividade)
- **GitHub Actions:**
  - **Passos:**
    1. Criar um arquivo `.github/workflows/ci.yml` no repositório.
    2. Exemplo de workflow básico:
       ```yaml
       name: CI Pipeline

       on: [push, pull_request]

       jobs:
         build:
           runs-on: ubuntu-latest
           steps:
             - name: Checkout code
               uses: actions/checkout@v2

             - name: Set up Node.js
               uses: actions/setup-node@v2
               with:
                 node-version: '14'

             - name: Install dependencies
               run: npm install

             - name: Run tests
               run: npm test
       ```
- **Jenkins:**
  - **Passos:**
    1. Instalar Jenkins e configurar.
    2. Criar um novo projeto freestyle.
    3. Configurar para usar o repositório Git.
    4. Adicionar steps para instalação de dependências e execução de testes.

#### **1.2 Testes automatizados em CI**
- **Objetivos:**
  - **Automação de testes:** Garantir que testes sejam executados automaticamente em cada commit.
  - **Feedback rápido:** Fornecer feedback imediato sobre a integridade do código.
- **Exemplos de Testes:**
  - **Unitários:** Testes de funções individuais.
  - **Integração:** Testes de múltiplos componentes funcionando juntos.
  - **End-to-end (E2E):** Testes que verificam o fluxo completo do aplicativo.

---

## **Atividade**
- **Configurar um pipeline CI para um projeto básico usando Azure DevOps:**
  - **Passos:**
    1. **Criar um projeto no Azure DevOps:**
       - Acesse [Azure DevOps](https://dev.azure.com/).
       - Crie um novo projeto ou use um existente.
    2. **Configurar Repositório:**
       - Crie ou use um repositório Git no projeto.
       - Adicione o código fonte do projeto.
    3. **Criar Pipeline CI:**
       - Navegue até **Pipelines** > **New Pipeline**.
       - Escolha o repositório e selecione **Starter pipeline**.
       - **Exemplo de Pipeline YAML:**
         ```yaml
         trigger:
         - main

         pool:
           vmImage: 'ubuntu-latest'

         steps:
         - task: NodeTool@0
           inputs:
             versionSpec: '14.x'
           displayName: 'Install Node.js'

         - script: |
             npm install
             npm test
           displayName: 'Run tests'
         ```
    4. **Executar e Monitorar:**
       - Salve e execute o pipeline.
       - Monitore o pipeline na interface do Azure DevOps.

---

## **Material de Apoio**

### **Slides**
- **[Introdução ao CI/CD](slides/intro-ci-cd.pdf)**: Conceitos básicos e arquitetura de CI/CD.
- **[Ferramentas de CI](slides/ferramentas-ci.pdf)**: Visão geral de Jenkins, GitHub Actions e Azure Pipelines.

### **Documentos**
- **[Guia de Configuração de Pipeline CI](docs/guia-configuracao-pipeline-ci.pdf)**: Instruções detalhadas para configurar pipelines CI.
- **[Guia de Testes Automatizados](docs/guia-testes-automatizados.pdf)**: Melhores práticas e exemplos de testes automatizados.

### **Vídeos**
- **[O que é CI/CD?](https://youtu.be/Scf8Xv2RDcY)**
- **[Tutorial de GitHub Actions](https://youtu.be/eB0nUzAI7M8)**
- **[Introdução ao Azure Pipelines](https://youtu.be/U4N6FcgkDJI)**

### **Links Úteis**
- [Documentação Jenkins](https://www.jenkins.io/doc/)
- [Documentação GitHub Actions](https://docs.github.com/actions)
- [Documentação Azure Pipelines](https://docs.microsoft.com/azure/devops/pipelines/)

---

**Dicas:**
- Verifique os logs do pipeline para depuração de erros.
- Explore as integrações de cada ferramenta com outras partes do fluxo de DevOps.
- Use boas práticas para nomenclatura e organização de pipelines.
