# aks-container-apps_globalazure-piracicaba-2026
Conteúdos da apresentação **Aplicações containerizadas no Azure: AKS ou Container Apps, qual a melhor solução?**.

LinkedIn: **https://www.linkedin.com/in/renatogroffe/**

Imagens:

- https://hub.docker.com/r/renatogroffe/dotnet10-worker-httprequest
- https://hub.docker.com/r/renatogroffe/dotnet10-job-httprequest

Projetos:
- https://github.com/renatogroffe/dotnet10-worker_httprequest
- https://github.com/renatogroffe/dotnet10-consoleapp_job-httprequest

---

QR Code

![QR Code](img/qrcode.png)

---

## Comparativo: Azure Kubernetes Service (AKS) vs Azure Container Apps

### Azure Kubernetes Service (AKS)
**Características Gerais:**
- Serviço gerenciado de Kubernetes.
- Ideal para workloads que exigem controle total sobre orquestração, rede, segurança e integração com o ecossistema Kubernetes.
- Suporta múltiplos pools de nós, Windows e Linux, GPUs, e integrações avançadas (Helm, Istio, etc).
- O plano de controle é gerenciado pela Azure, mas o usuário gerencia os nós de trabalho.

**Vantagens:**
- Flexibilidade máxima para workloads complexos e personalizados.
- Suporte a workloads de missão crítica, alta disponibilidade e compliance.
- Integração nativa com ferramentas open source e DevOps.
- Escalabilidade horizontal e vertical avançada.
- Suporte a workloads stateful e stateless.

**Desvantagens:**
- Maior complexidade operacional (gestão de clusters, upgrades, rede, etc).
- Requer conhecimento de Kubernetes.
- O usuário é responsável por parte da manutenção e segurança dos nós de trabalho.
- Custo pode ser maior para workloads pequenos ou intermitentes.

---

### Azure Container Apps
**Características Gerais:**
- Plataforma serverless para containers, baseada em Kubernetes, mas abstrai a complexidade do cluster.
- Foco em simplicidade operacional, escalabilidade automática e redução de custos.
- Ideal para APIs, microsserviços, jobs de background e workloads event-driven.
- Suporte a autoscaling (incluindo scale-to-zero), Dapr, KEDA, revisões, blue/green deployment, e integração com Azure Functions.

**Vantagens:**
- Não requer conhecimento de Kubernetes.
- Gerenciamento de infraestrutura totalmente automatizado.
- Escalabilidade automática baseada em eventos, HTTP, CPU/memória, etc.
- Paga apenas pelo consumo (escala até zero).
- Fácil integração com outros serviços Azure e recursos de segurança (VNet, managed identity, secrets).

**Desvantagens:**
- Menor flexibilidade para customizações avançadas de cluster e rede.
- Não expõe toda a API do Kubernetes.
- Pode não atender workloads que exigem controle detalhado de infraestrutura.
- Algumas limitações para workloads stateful complexos.

---

### Resumo

|                     | AKS                                         | Container Apps                                 |
|---------------------|---------------------------------------------|------------------------------------------------|
| **Gerenciamento**   | Kubernetes gerenciado, mas com controle     | Totalmente serverless, abstrai o cluster       |
| **Escalabilidade**  | Avançada, manual ou automática              | Totalmente automática, inclusive scale-to-zero |
| **Complexidade**    | Alta, exige conhecimento de Kubernetes      | Baixa, foco em simplicidade                    |
| **Casos de uso**    | Workloads complexos, customizados, críticos | APIs, microsserviços, jobs, event-driven       |
| **Custo**           | Paga pelos nós provisionados                | Paga pelo consumo real                         |
| **Customização**    | Máxima                                      | Limitada                                       |

---

Conteúdo baseado na documentação oficial do Microsoft Learn (MCP).