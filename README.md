<h1 align="center">
    <img align="center" src="https://logospng.org/download/uol/logo-uol-icon-256.png" width="40" height="40" /> Compass UOL - DevSecOps
</h1>

# Projeto de Modernização de Infraestrutura na AWS

## 📌 Visão Geral

Este projeto tem como objetivo migrar a infraestrutura de um e-commerce para a AWS, garantindo alta disponibilidade, escalabilidade e segurança. A transição ocorre em duas fases: 

1. **Migração "As-Is" (Lift-and-Shift)**: Transferência rápida da infraestrutura on-premises para a AWS.
2. **Modernização**: Implementação de uma arquitetura baseada em Kubernetes para otimizar a performance e a gestão dos serviços.

## 🏗 Arquitetura do Projeto

### 🔹 Situação Atual
A infraestrutura atual consiste em:
- **Banco de Dados**: MySQL (500GB de dados, 10GB de RAM, 3 Core CPU)
- **Frontend**: React (5GB de dados, 2GB de RAM, 1 Core CPU)
- **Backend**:
  - 3 APIs
  - Nginx como balanceador de carga
  - Armazenamento de arquivos estáticos (5GB de dados, 4GB de RAM, 2 Core CPU)

### 🔹 Arquitetura na AWS
A nova infraestrutura na AWS segue os pilares da AWS Well-Architected Framework e será dividida em duas etapas:

![Pilares da AWS Well-Architected Framework](img/pilares_aws.png)

#### 🛠 **Fase 1: Lift-and-Shift (Migração As-Is)**
- **Migração dos servidores on-premises para a AWS** utilizando o AWS Application Migration Service (MGN).
- **Infraestrutura baseada em Amazon EC2** com balanceamento de carga via Elastic Load Balancing.
- **Banco de dados migrado para Amazon RDS (MySQL)** com Multi-AZ habilitado.
- **Armazenamento de arquivos no Amazon S3**.
- **Monitoramento e logging com Amazon CloudWatch e AWS X-Ray**.

#### 🚀 **Fase 2: Modernização com Kubernetes**
- **Containers gerenciados pelo Amazon EKS** para melhorar a escalabilidade.
- **Imagens armazenadas no Amazon ECR**.
- **Armazenamento compartilhado via Amazon EFS**.
- **Gerenciamento de tráfego com Amazon Route 53 e Amazon CloudFront**.
- **Segurança reforçada com AWS WAF e AWS Secrets Manager**.

## 🏛 Serviços AWS Utilizados

Ícone | **Serviço AWS** | **Função no Projeto** |
|--- | --- | --- |
| <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRULf2JOHbvkPux8pEzQrkH70TVSpfgRMzgQA&s" width="50"> | **Amazon EC2** | Hospedar e executar as aplicações e serviços essenciais. |
| <img src="https://cloud-icons.onemodel.app/aws/Resource-Icons_01312023/Res_Networking-and-Content-Delivery/Res_48_Light/Res_Elastic-Load-Balancing_Application-Load-Balancer_48_Light.png" width="50"> | **Application Load Balancer** | Distribuir o tráfego. |
| <img src="https://cloud-icons.onemodel.app/aws/Architecture-Service-Icons_01312023/Arch_Migration-Transfer/64/Arch_AWS-Application-Migration-Service_64@5x.png" width="50"> | **AWS Application Migration Service (MGN)** | Automatizar a migração de servidores. |
| <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ7L7fI-Ozxh2ni9T2E7rgX_CU-VNMOpoXfwpIxYIaifUcJL_NQ0ZJi8mGHWNRdiFXmres&usqp=CAU" width="50"> | **Amazon RDS for MySQL** | Banco de dados relacional gerenciado. |
| <img src="https://github.com/user-attachments/assets/74224709-c040-46dd-858c-6307886fb90d" width="50"> | **Amazon VPC** | Criar uma rede isolada e segura. |
| <img src="https://cloud-icons.onemodel.app/aws/Resource-Icons_01312023/Res_Networking-and-Content-Delivery/Res_48_Light/Res_Amazon-VPC_NAT-Gateway_48_Light.png" width="50"> | NAT (Network Address Translation) | Serviço de tradução de endereços de rede. |
| <img src="https://cloud-icons.onemodel.app/aws/Resource-Icons_01312023/Res_Networking-and-Content-Delivery/Res_48_Light/Res_Amazon-VPC_Internet-Gateway_48_Light.png" width="50"> | Internet Gateway | Componente de rede para comunicação com a Internet. |
| <img src="https://cdn.worldvectorlogo.com/logos/amazon-s3-simple-storage-service.svg" width="50"> | **Amazon S3** | Armazenamento escalável para arquivos e backups. |
| <img src="https://cloud-icons.onemodel.app/aws/Architecture-Service-Icons_01312023/Arch_Storage/64/Arch_Amazon-Simple-Storage-Service-Glacier_64.svg" width="50"> | **S3 Glacier Instant Retrieval** | Armazenamento de longo prazo. |
| <img src="https://cloud-icons.onemodel.app/aws/Architecture-Service-Icons_01312023/Arch_Management-Governance/64/Arch_Amazon-CloudWatch_64.png" width="50"> | **Amazon CloudWatch** | Monitoramento de métricas e logs. |
| <img src="https://cloud-icons.onemodel.app/aws/Architecture-Service-Icons_01312023/Arch_Containers/64/Arch_Amazon-Elastic-Kubernetes-Service_64.png" width="50"> | **Amazon EKS** | Orquestração de containers Kubernetes. |
| <img src="https://cloud-icons.onemodel.app/aws/Architecture-Service-Icons_01312023/Arch_Networking-Content-Delivery/64/Arch_Amazon-Route-53_64@5x.png" width="50"> | **Amazon Route 53** | Gerenciamento de DNS. |
| <img src="https://cloud-icons.onemodel.app/aws/Architecture-Service-Icons_01312023/Arch_Storage/64/Arch_Amazon-EFS_64.svg" width="50"> | **Amazon EFS** | Armazenamento compartilhado para múltiplas instâncias. |
| <img src="https://cloud-icons.onemodel.app/aws/Architecture-Service-Icons_01312023/Arch_Containers/64/Arch_Amazon-Elastic-Container-Registry_64.png" width="50"> | **Amazon ECR** | Armazenamento de imagens Docker. |
| <img src="https://cloud-icons.onemodel.app/aws/Architecture-Service-Icons_01312023/Arch_Security-Identity-Compliance/64/Arch_AWS-WAF_64.png" width="50"> | **AWS WAF** | Proteção contra ataques na camada web. |
| <img src="https://cloud-icons.onemodel.app/aws/Architecture-Service-Icons_01312023/Arch_Networking-Content-Delivery/64/Arch_Amazon-CloudFront_64.png" width="50"> | **Amazon CloudFront** | Distribuição de conteúdo globalmente. |
| <img src="https://cloud-icons.onemodel.app/aws/Architecture-Service-Icons_01312023/Arch_Security-Identity-Compliance/64/Arch_AWS-Secrets-Manager_64@5x.png" width="50"> | **AWS Secrets Manager** | Gestão segura de credenciais. |
| <img src="https://cloud-icons.onemodel.app/aws/Architecture-Service-Icons_01312023/Arch_Storage/64/Arch_AWS-Backup_64@5x.png" width="50"> | **AWS Backup** | Automação e gerenciamento de backups. |
| <img src="https://cloud-icons.onemodel.app/aws/Architecture-Service-Icons_01312023/Arch_Developer-Tools/64/Arch_AWS-CodeBuild_64.svg" width="50"> | **AWS CodeBuild** | Construção e testes automáticos no CI/CD. |
| <img src="https://cloud-icons.onemodel.app/aws/Architecture-Service-Icons_01312023/Arch_Developer-Tools/64/Arch_AWS-CodePipeline_64.svg" width="50"> | **AWS CodePipeline** | Fluxo automatizado de CI/CD. |
| <img src="https://cloud-icons.onemodel.app/aws/Architecture-Service-Icons_01312023/Arch_Developer-Tools/64/Arch_AWS-CodeCommit_64.svg" width="50"> | **AWS CodeCommit** | Repositório Git seguro para armazenar o código-fonte do projeto. |
| <img src="https://cloud-icons.onemodel.app/aws/Architecture-Service-Icons_01312023/Arch_Developer-Tools/64/Arch_AWS-CodeDeploy_64.svg" width="50"> | **AWS CodeDeploy** | Automatizar implantações de código para EC2, EKS e outros serviços AWS. |

## 📊 Diagramas da Arquitetura

1. **Fase 1: Migração (Lift-and-Shift)**
   ![Diagrama de Migração](img/migracao.drawio.png)

2. **Infraestrutura Pós-Migração**
   ![Diagrama Pós-Migração](img/posmigracao.drawio.png)
   
3. **Fase 2: Modernização (Kubernetes)**
   ![Diagrama de Modernização](img/modernizacao.drawio.png)

4. **Fluxo de Deploy**
   ![deploy-Página-1](https://github.com/user-attachments/assets/a05fc21f-50d3-43a7-8402-200c28b3cc22)



## 💰 Estimativa de Custos na AWS
A estimativa de custos foi calculada utilizando a ferramenta **AWS Pricing Calculator**.

📄 Detalhes da estimativa podem ser encontrados no arquivo: [Estimativa AWS Calculator](aws_calculator.pdf)

## 📜 Conclusão
O projeto propõe uma migração eficiente e uma modernização segura, garantindo um ambiente de alta disponibilidade e escalabilidade na AWS. A infraestrutura planejada atende às necessidades do cliente, promovendo melhor desempenho e segurança para o e-commerce.

---

✍ **Desenvolvido por:** 

<h1 align="center">
    <img align="center" src="https://logospng.org/download/uol/logo-uol-icon-256.png" width="40" height="40" /> Compass UOL - DevSecOps
</h1>





