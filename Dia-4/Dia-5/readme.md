# **Curso de Introdução ao SRE e DevOps**

## **Dia 5: Monitoramento e Observabilidade**

### **Sumário**
- [Sessão Teórica](#sessão-teórica)
  - [Monitoramento e Observabilidade](#1-monitoramento-e-observabilidade)
    - [Conceitos de Monitoramento e Observabilidade](#11-conceitos-de-monitoramento-e-observabilidade)
    - [Ferramentas: Prometheus, Grafana, Loki](#12-ferramentas-prometheus-grafana-loki)
- [Sessão Prática](#sessão-prática)
  - [Configuração de Monitoramento](#1-configuração-de-monitoramento)
    - [Implementar Prometheus e Grafana em um cluster Kubernetes](#11-implementar-prometheus-e-grafana-em-um-cluster-kubernetes)
    - [Configurar alertas básicos](#12-configurar-alertas-básicos)
- [Atividade](#atividade)
- [Material de Apoio](#material-de-apoio)

---

## **Sessão Teórica**

### **1. Monitoramento e Observabilidade**

#### **1.1 Conceitos de Monitoramento e Observabilidade**
- **Monitoramento:**
  - **Definição:** Processo de coleta de dados de desempenho, utilização e disponibilidade de sistemas e aplicações.
  - **Objetivo:** Fornecer informações sobre a saúde do sistema e identificar problemas.
- **Observabilidade:**
  - **Definição:** Capacidade de entender o comportamento interno de um sistema com base em sua saída externa, como logs, métricas e rastreamentos.
  - **Objetivo:** Facilitar a detecção, diagnóstico e correção de problemas em sistemas complexos.

#### **1.2 Ferramentas: Prometheus, Grafana, Loki**
- **Prometheus:**
  - **Função:** Sistema de monitoramento e alerta.
  - **Recursos:** Coleta de métricas, consultas, alertas e armazenamento de dados em séries temporais.
- **Grafana:**
  - **Função:** Plataforma de visualização e análise de dados.
  - **Recursos:** Dashboards interativos, integrações com várias fontes de dados, incluindo Prometheus.
- **Loki:**
  - **Função:** Sistema de gerenciamento e consulta de logs.
  - **Recursos:** Armazenamento de logs, integração com Grafana, consultas baseadas em rótulos.

---

## **Sessão Prática**

### **1. Configuração de Monitoramento**

#### **1.1 Implementar Prometheus e Grafana em um cluster Kubernetes**
- **Passos:**
  1. **Instalar Prometheus:**
     - Adicione o repositório Helm para Prometheus:
       ```bash
       helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
       helm repo update
       ```
     - Instale o Prometheus usando Helm:
       ```bash
       helm install prometheus prometheus-community/prometheus --namespace monitoring --create-namespace
       ```
  2. **Instalar Grafana:**
     - Adicione o repositório Helm para Grafana:
       ```bash
       helm repo add grafana https://grafana.github.io/helm-charts
       helm repo update
       ```
     - Instale o Grafana usando Helm:
       ```bash
       helm install grafana grafana/grafana --namespace monitoring
       ```
     - **Acessar Grafana:**
       - Obtenha a senha do administrador:
         ```bash
         kubectl get secret --namespace monitoring grafana -o jsonpath="{.data.admin-password}" | base64 --decode ; echo
         ```
       - Acesse Grafana via `http://<Grafana-Service-IP>:3000` com o usuário `admin` e a senha obtida.

  3. **Configurar Prometheus como fonte de dados no Grafana:**
     - Acesse a interface do Grafana.
     - Navegue até **Configuration** > **Data Sources**.
     - Adicione uma nova fonte de dados e selecione **Prometheus**.
     - Defina a URL como `http://prometheus-server.monitoring.svc.cluster.local`.

#### **1.2 Configurar alertas básicos**
- **Passos:**
  1. **Configurar Alertmanager para Prometheus:**
     - Edite o `prometheus.yaml` para incluir configurações de Alertmanager:
       ```yaml
       alerting:
         alertmanagers:
         - static_configs:
           - targets:
             - alertmanager.monitoring.svc.cluster.local:9093
       ```
     - Crie regras de alerta básicas:
       ```yaml
       groups:
       - name: example-alerts
         rules:
         - alert: InstanceDown
           expr: up == 0
           for: 5m
           labels:
             severity: page
           annotations:
             summary: "Instance {{ $labels.instance }} down"
             description: "{{ $labels.instance }} de {{ $labels.job }} está fora do ar."
       ```
     - Aplique as regras ao Prometheus.
  2. **Configurar Alertas no Grafana:**
     - Navegue até **Alerting** > **Alert Rules**.
     - Crie uma nova regra de alerta baseada nas métricas fornecidas pelo Prometheus.

---

## **Atividade**
- **Configurar dashboards no Grafana e alertas no Prometheus:**
  - **Passos:**
    1. **Criar Dashboards:**
       - Navegue até **Create** > **Dashboard** no Grafana.
       - Adicione **Painéis** com gráficos baseados em métricas Prometheus.
    2. **Configurar Alertas:**
       - Adicione novas **regras de alerta** no Prometheus para monitorar métricas críticas.
       - Configure notificações para alertas críticos via Grafana ou Prometheus.

---

## **Material de Apoio**

### **Slides**
- **[Monitoramento e Observabilidade](slides/monitoramento-observabilidade.pdf)**: Conceitos e ferramentas para monitoramento e observabilidade.
- **[Introdução ao Prometheus e Grafana](slides/intro-prometheus-grafana.pdf)**: Visão geral e configuração inicial.

### **Documentos**
- **[Guia de Configuração de Prometheus](docs/guia-configuracao-prometheus.pdf)**: Passo a passo para configurar Prometheus.
- **[Guia de Configuração de Grafana](docs/guia-configuracao-grafana.pdf)**: Instruções detalhadas para criar e configurar dashboards no Grafana.

### **Vídeos**
- **[O que é Observabilidade?](https://youtu.be/NZ7Jl_2cZ_Y)**
- **[Tutorial de Prometheus e Grafana](https://youtu.be/zl0J_Y7D2ow)**

### **Links Úteis**
- [Documentação Prometheus](https://prometheus.io/docs/introduction/overview/)
- [Documentação Grafana](https://grafana.com/docs/grafana/latest/)
- [Documentação Loki](https://grafana.com/docs/loki/latest/)

---

**Dicas:**
- Verifique os logs do Prometheus e Grafana para depuração.
- Explore diferentes tipos de gráficos e painéis no Grafana.
- Configure alertas e notificações para manter a equipe informada sobre a saúde do sistema.
