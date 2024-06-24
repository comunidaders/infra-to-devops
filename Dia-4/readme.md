# **Curso de Introdução ao SRE e DevOps**

## **Dia 4: Entrega e Implantação Contínua (CD)**

### **Sumário**
- [Sessão Teórica](#sessão-teórica)
  - [CD](#1-cd)
    - [Conceitos de Entrega Contínua e Implantação Contínua](#11-conceitos-de-entrega-contínua-e-implantação-contínua)
    - [Estratégias de Deploy: Blue-Green, Canary](#12-estratégias-de-deploy-blue-green-canary)
- [Sessão Prática](#sessão-prática)
  - [Pipeline CD](#1-pipeline-cd)
    - [Criar e configurar um pipeline de CD para deploy automatizado em Kubernetes](#11-criar-e-configurar-um-pipeline-de-cd-para-deploy-automatizado-em-kubernetes)
- [Atividade](#atividade)
- [Material de Apoio](#material-de-apoio)

---

## **Sessão Teórica**

### **1. CD**

#### **1.1 Conceitos de Entrega Contínua e Implantação Contínua**
- **Entrega Contínua (CD):**
  - **Definição:** Processo de manter o código pronto para ser liberado a qualquer momento.
  - **Objetivo:** Garantir que o software possa ser implantado em qualquer ambiente com um clique de botão ou comando.
- **Implantação Contínua:**
  - **Definição:** Extensão da Entrega Contínua onde cada mudança que passa pelos testes automatizados é automaticamente implantada em produção.
  - **Objetivo:** Minimizar o tempo de entrega de novas funcionalidades para os usuários finais.

#### **1.2 Estratégias de Deploy: Blue-Green, Canary**
- **Blue-Green Deployment:**
  - **Definição:** Método que reduz o tempo de inatividade e os riscos com dois ambientes, Blue (produção atual) e Green (nova versão).
  - **Processo:** O tráfego é direcionado para o ambiente Green após a implantação bem-sucedida, mantendo o Blue como fallback.
- **Canary Deployment:**
  - **Definição:** Técnica onde uma nova versão é lançada para um subconjunto de usuários antes de uma implantação completa.
  - **Processo:** Monitoramento de performance e erros no grupo Canary antes de liberar para todos os usuários.

---

## **Sessão Prática**

### **1. Pipeline CD**

#### **1.1 Criar e configurar um pipeline de CD para deploy automatizado em Kubernetes**
- **Ferramenta Utilizada:** Azure DevOps
- **Passos:**
  1. **Criar um Serviço de Conexão Kubernetes no Azure DevOps:**
     - Acesse **Project Settings** > **Service connections** > **New service connection**.
     - Escolha **Kubernetes**, configure e conecte ao seu cluster Kubernetes.

  2. **Configurar o pipeline CD no Azure DevOps:**
     - Navegue até **Pipelines** > **Releases** > **New pipeline**.
     - Escolha **Empty job** para criar um pipeline de CD do zero.

  3. **Adicionar Artefatos:**
     - Adicione a **fonte de artefatos** (como um build anterior) que contém a imagem Docker ou o helm chart.

  4. **Configurar Tarefas do Pipeline CD:**
     - Adicione tarefas para implantar a aplicação no Kubernetes.

     **Exemplo de Pipeline YAML:**
     ```yaml
     trigger:
     - main

     pool:
       vmImage: 'ubuntu-latest'

     steps:
     - task: Kubernetes@1
       inputs:
         connectionType: 'Kubernetes Service Connection'
         kubernetesServiceEndpoint: '<nome-do-serviço-de-conexão>'
         namespace: 'default'
         command: 'apply'
         useConfigurationFile: true
         configuration: '$(Pipeline.Workspace)/manifests/deployment.yaml'
         secretType: 'dockerRegistry'
         secretName: '<nome-do-segredo>'
     ```

  5. **Configurar Aprovações e Checks:**
     - Defina aprovações e condições de gatilho para o deploy em produção.

  6. **Executar e Monitorar:**
     - Salve, execute e monitore o pipeline.
     - Verifique os logs e o status do deployment.

---

## **Atividade**
- **Configurar um pipeline CD para implantar uma aplicação no Kubernetes usando Azure DevOps:**
  - **Passos:**
    1. **Criar Artefatos:** Garanta que os artefatos (imagens Docker, helm charts, etc.) estejam prontos para deploy.
    2. **Configurar Pipeline CD:** Siga os passos da seção prática para configurar o pipeline de CD.
    3. **Deploy Automatizado:** Valide que a aplicação foi implantada corretamente no cluster Kubernetes.
    4. **Teste e Verifique:** Execute testes e verifique se a aplicação está funcionando conforme esperado.

---

## **Material de Apoio**

### **Slides**
- **[Introdução ao CD](slides/intro-cd.pdf)**: Conceitos básicos e estratégias de deploy.
- **[Estratégias de Deploy](slides/estrategias-deploy.pdf)**: Blue-Green e Canary deployments.

### **Documentos**
- **[Guia de Configuração de Pipeline CD](docs/guia-configuracao-pipeline-cd.pdf)**: Instruções detalhadas para configurar pipelines de CD.
- **[Guia de Deploy em Kubernetes](docs/guia-deploy-kubernetes.pdf)**: Passo a passo para deploy em Kubernetes com Azure DevOps.

### **Vídeos**
- **[O que é Entrega Contínua?](https://youtu.be/LvbKR32RW_w)**
- **[Tutorial de Azure Pipelines para CD](https://youtu.be/5cdD5SCg3Ls)**

### **Links Úteis**
- [Documentação Azure Pipelines](https://docs.microsoft.com/azure/devops/pipelines/)
- [Documentação Kubernetes](https://kubernetes.io/docs/home/)

---

**Dicas:**
- Verifique os logs de implantação e monitore o aplicativo após o deploy.
- Utilize as práticas recomendadas para configurar segredos e acesso ao cluster.
- Adapte as estratégias de deploy conforme o contexto e as necessidades do projeto.
