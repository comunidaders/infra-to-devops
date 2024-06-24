# **Curso de Introdução ao SRE e DevOps**

## **Dia 6: Segurança e Automação de Infraestrutura**

### **Sumário**
- [Sessão Teórica](#sessão-teórica)
  - [Segurança em DevOps](#1-segurança-em-devops)
    - [Práticas de DevSecOps](#11-práticas-de-devsecops)
    - [Ferramentas de Segurança: Scan de Vulnerabilidades, RBAC](#12-ferramentas-de-segurança-scan-de-vulnerabilidades-rbac)
  - [Infraestrutura como Código (IaC)](#2-infraestrutura-como-código-iac)
    - [Introdução ao Terraform](#21-introdução-ao-terraform)
- [Sessão Prática](#sessão-prática)
  - [Infraestrutura como Código (IaC)](#1-infraestrutura-como-código-iac-1)
    - [Criar e aplicar um plano Terraform para provisionar recursos](#11-criar-e-aplicar-um-plano-terraform-para-provisionar-recursos)
- [Atividade](#atividade)
- [Material de Apoio](#material-de-apoio)

---

## **Sessão Teórica**

### **1. Segurança em DevOps**

#### **1.1 Práticas de DevSecOps**
- **Definição:**
  - DevSecOps integra práticas de segurança em todas as fases do ciclo de vida do DevOps.
- **Objetivos:**
  - **Automação:** Automatizar verificações de segurança.
  - **Monitoramento Contínuo:** Implementar práticas de segurança como parte do processo de desenvolvimento.
  - **Colaboração:** Integrar equipes de desenvolvimento, operações e segurança.
- **Práticas Principais:**
  - **Shift-Left:** Integrar segurança desde o início do desenvolvimento.
  - **Testes de Segurança Automatizados:** Incluem scans de vulnerabilidades, análise de código e testes de penetração.
  - **Respostas a Incidentes:** Planejamento e resposta rápida a falhas de segurança.

#### **1.2 Ferramentas de Segurança: Scan de Vulnerabilidades, RBAC**
- **Scan de Vulnerabilidades:**
  - **Objetivo:** Identificar e corrigir vulnerabilidades em códigos e sistemas.
  - **Ferramentas Populares:**
    - **Snyk:** Análise de segurança para projetos Node.js.
    - **Aqua Security:** Segurança para contêineres e aplicações nativas de nuvem.
- **RBAC (Role-Based Access Control):**
  - **Objetivo:** Controle de acesso baseado em funções para garantir segurança granular.
  - **Ferramentas Populares:**
    - **Kubernetes RBAC:** Gerenciamento de permissões em Kubernetes.
    - **Azure RBAC:** Controle de acesso baseado em funções na Azure.

### **2. Infraestrutura como Código (IaC)**

#### **2.1 Introdução ao Terraform**
- **Definição:**
  - Terraform é uma ferramenta de IaC que permite definir e provisionar a infraestrutura através de código.
- **Objetivos:**
  - **Automação:** Provisão e gerenciamento de infraestrutura de forma automática e repetível.
  - **Versão:** Manter a infraestrutura sob controle de versão.
- **Conceitos Básicos:**
  - **Configuração:** Infraestrutura definida em arquivos `.tf`.
  - **Plan:** Gera um plano de execução das alterações.
  - **Apply:** Aplica as alterações definidas no plano.
- **Componentes Principais:**
  - **Providers:** Integram o Terraform com serviços de nuvem e outros sistemas.
  - **Resources:** Elementos que são criados e gerenciados pelo Terraform.
  - **Modules:** Conjuntos reutilizáveis de configurações do Terraform.

---

## **Sessão Prática**

### **1. Infraestrutura como Código (IaC)**

#### **1.1 Criar e aplicar um plano Terraform para provisionar recursos**
- **Passos:**
  1. **Instalar Terraform:**
     - **Instruções:** [Documentação Terraform](https://learn.hashicorp.com/tutorials/terraform/install-cli)
  2. **Configurar um Plano Terraform:**
     - **Exemplo de configuração:**
       ```hcl
       provider "azurerm" {
         features {}
       }

       resource "azurerm_resource_group" "example" {
         name     = "rg-example"
         location = "East US"
       }

       resource "azurerm_storage_account" "example" {
         name                     = "storageaccountname"
         resource_group_name      = azurerm_resource_group.example.name
         location                 = azurerm_resource_group.example.location
         account_tier             = "Standard"
         account_replication_type = "LRS"
       }
       ```
     - **Comandos:**
       ```bash
       terraform init
       terraform plan
       terraform apply
       ```
  3. **Aplicar o Plano:**
     - Execute `terraform apply` para provisionar os recursos.

---

## **Atividade**
- **Criar um script Terraform para provisionar uma VM ou bucket de armazenamento:**
  - **Passos:**
    1. **Escolher o recurso para provisionar (VM ou bucket):**
       - VM: Defina a configuração da máquina virtual no script.
       - Bucket: Configure um bucket de armazenamento na nuvem.
    2. **Escrever o Script Terraform:**
       - Use exemplos fornecidos na sessão prática.
       - Adapte as configurações conforme necessário.
    3. **Aplicar o Script:**
       - Execute `terraform init`, `terraform plan` e `terraform apply`.

---

## **Material de Apoio**

### **Slides**
- **[Segurança em DevOps](slides/seguranca-devops.pdf)**: Práticas de segurança e DevSecOps.
- **[Introdução ao Terraform](slides/introducao-terraform.pdf)**: Conceitos básicos e primeiros passos com Terraform.

### **Documentos**
- **[Guia de Práticas de DevSecOps](docs/guia-praticas-devsecops.pdf)**: Instruções detalhadas para integrar segurança ao DevOps.
- **[Guia de Terraform](docs/guia-terraform.pdf)**: Passo a passo para criar e aplicar planos com Terraform.

### **Vídeos**
- **[O que é DevSecOps?](https://youtu.be/W5mRsosS0TY)**
- **[Tutorial de Terraform](https://youtu.be/Yl6sb2GcvQ0)**

### **Links Úteis**
- [Documentação Terraform](https://www.terraform.io/docs/index.html)
- [Documentação Kubernetes RBAC](https://kubernetes.io/docs/reference/access-authn-authz/rbac/)
- [Documentação Snyk](https://snyk.io/docs/)

---

**Dicas:**
- Teste os scripts Terraform em um ambiente seguro antes de aplicá-los em produção.
- Utilize práticas de segurança como análise estática e verificação de vulnerabilidades em seus scripts.
- Mantenha os scripts sob controle de versão para rastrear alterações e garantir a reprodutibilidade.
