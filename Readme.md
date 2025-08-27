# Relatório de Implementação de Serviços AWS

**Data:** 24/08/2025  
**Empresa:** Abstergo Industries  
**Responsável:** Anthony Mahyhaker Silva

## Introdução

Este relatório apresenta o processo de implementação de ferramentas na empresa Abstergo Industries, realizado por Anthony Mahyhaker Silva. O objetivo do projeto foi elencar 3 serviços AWS, com a finalidade de realizar diminuição de custos imediatos.

---

## Etapa 1:
- **Amazon EC2 (Elastic Compute Cloud)**
- **Computação em Nuvem Escalável**
- **Migração dos servidores físicos locais para instâncias virtuais na nuvem, permitindo redução de custos com hardware, manutenção e energia elétrica. O EC2 oferece capacidade de processamento redimensionável com modelo de pagamento sob demanda (pay-as-you-use), eliminando investimentos iniciais em infraestrutura física.**

## Etapa 2:
- **Amazon S3 (Simple Storage Service)**
- **Armazenamento de Dados na Nuvem**
- **Substituição dos sistemas de backup e armazenamento local por uma solução de armazenamento em nuvem altamente durável e disponível. O S3 elimina a necessidade de investimento em hardware de armazenamento, reduz custos operacionais e oferece diferentes classes de armazenamento para otimização de custos baseada na frequência de acesso aos dados.**

## Etapa 3:
- **Amazon RDS (Relational Database Service)**
- **Banco de Dados Gerenciado**
- **Migração dos bancos de dados locais para um serviço totalmente gerenciado, eliminando custos com licenças de software, hardware dedicado, administração de banco de dados e manutenção. O RDS automatiza tarefas como backup, recuperação, monitoramento e atualizações de segurança, reduzindo significativamente os custos operacionais.**

---

## Conclusão

A implementação dos três serviços AWS (EC2, S3 e RDS) na Abstergo Industries resultará em uma redução significativa de custos operacionais através da eliminação de investimentos em hardware físico, redução de custos com energia, manutenção e pessoal técnico especializado. 

### Benefícios Alcançados:
- **Redução de CAPEX:** Eliminação de investimentos iniciais em servidores, sistemas de armazenamento e licenças de software
- **Otimização de OPEX:** Modelo de pagamento sob demanda reduz custos operacionais mensais
- **Escalabilidade:** Recursos podem ser ajustados conforme demanda, evitando superdimensionamento
- **Alta Disponibilidade:** Infraestrutura distribuída garante continuidade do negócio
- **Segurança Aprimorada:** Proteção avançada sem custos adicionais de implementação

### Projeção de Economia:
- **Curto prazo (6 meses):** Redução estimada de 30% nos custos de TI
- **Médio prazo (12 meses):** Redução estimada de 45% nos custos totais de infraestrutura
- **Longo prazo (24 meses):** ROI positivo com economia acumulada de até 60%

### Recomendações para Próximas Etapas:
1. **Monitoramento contínuo** de custos através do AWS Cost Explorer
2. **Implementação de políticas** de auto-scaling para otimização adicional
3. **Avaliação de Reserved Instances** para cargas de trabalho estáveis
4. **Treinamento da equipe** para maximizar benefícios da plataforma AWS

---

# Projeto Farmácia Virtual AWS
*Plataforma de E-commerce Farmacêutico com Infraestrutura em Nuvem*

## 📋 Visão Geral do Projeto

Este projeto consiste na criação de uma plataforma web completa para uma farmácia fictícia, utilizando diversos serviços da Amazon Web Services (AWS). O objetivo é simular um ambiente real de e-commerce farmacêutico, abordando desde a interface do usuário até a infraestrutura backend robusta e segura.

## 🎯 Objetivos de Aprendizado

- Compreender e aplicar serviços fundamentais da AWS
- Implementar arquitetura de microsserviços na nuvem
- Configurar segurança e conformidade para dados sensíveis
- Desenvolver habilidades em DevOps e CI/CD
- Gerenciar custos e monitoramento de infraestrutura

## 🏗️ Arquitetura da Solução

### Frontend (Camada de Apresentação)
- **Amazon S3** + **CloudFront**: Hospedagem de site estático com CDN global
- **Route 53**: Gerenciamento de DNS personalizado
- **AWS Certificate Manager**: Certificados SSL/TLS gratuitos

### Backend (Camada de Aplicação)
- **Amazon EC2** ou **AWS Lambda**: Processamento de lógica de negócio
- **Application Load Balancer (ALB)**: Distribuição de carga
- **Amazon API Gateway**: Gerenciamento de APIs RESTful
- **AWS Elastic Beanstalk**: Deploy simplificado de aplicações

### Banco de Dados
- **Amazon RDS** (MySQL/PostgreSQL): Dados estruturados (produtos, usuários, pedidos)
- **Amazon DynamoDB**: Dados NoSQL (carrinho de compras, sessões)
- **Amazon ElastiCache**: Cache Redis para performance

### Armazenamento e Mídia
- **Amazon S3**: Imagens de produtos, documentos, backups
- **AWS Lambda**: Processamento de imagens (redimensionamento automático)

### Segurança e Conformidade
- **AWS IAM**: Controle de acesso granular
- **AWS Secrets Manager**: Gerenciamento de credenciais
- **AWS WAF**: Firewall de aplicações web
- **AWS Shield**: Proteção contra DDoS
- **VPC**: Rede virtual privada isolada

### Monitoramento e Logs
- **Amazon CloudWatch**: Métricas e alarmes
- **AWS CloudTrail**: Auditoria de ações
- **Amazon SNS**: Notificações por email/SMS

## 📦 Funcionalidades da Plataforma

### Portal do Cliente
- Cadastro e autenticação de usuários
- Catálogo de medicamentos com busca avançada
- Carrinho de compras persistente
- Histórico de pedidos
- Sistema de prescrições digitais
- Chat de atendimento online

### Portal Administrativo
- Gestão de estoque e produtos
- Processamento de pedidos
- Relatórios de vendas
- Controle de fornecedores
- Dashboard analítico

### APIs e Integrações
- API de verificação de prescrições
- Integração com sistemas de pagamento
- API de rastreamento de entrega
- Webhook para notificações

## 🛠️ Implementação Passo a Passo

### Fase 1: Configuração Inicial (Semana 1-2)
1. **Configuração da Conta AWS**
   - Criação de conta AWS
   - Configuração de billing alerts
   - Setup inicial do AWS CLI

2. **Rede e Segurança**
   ```bash
   # Criação de VPC
   aws ec2 create-vpc --cidr-block 10.0.0.0/16
   
   # Configuração de subnets públicas e privadas
   aws ec2 create-subnet --vpc-id vpc-12345 --cidr-block 10.0.1.0/24
   ```

### Fase 2: Base de Dados (Semana 2-3)
1. **Amazon RDS Setup**
   ```sql
   -- Schema principal
   CREATE DATABASE pharmacy_db;
   
   CREATE TABLE users (
       user_id INT AUTO_INCREMENT PRIMARY KEY,
       email VARCHAR(255) UNIQUE,
       password_hash VARCHAR(255),
       created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
   );
   
   CREATE TABLE products (
       product_id INT AUTO_INCREMENT PRIMARY KEY,
       name VARCHAR(255),
       description TEXT,
       price DECIMAL(10,2),
       stock_quantity INT,
       requires_prescription BOOLEAN
   );
   ```

2. **DynamoDB Tables**
   ```json
   {
     "TableName": "shopping_cart",
     "KeySchema": [
       {
         "AttributeName": "user_id",
         "KeyType": "HASH"
       }
     ],
     "AttributeDefinitions": [
       {
         "AttributeName": "user_id",
         "AttributeType": "S"
       }
     ]
   }
   ```

### Fase 3: Backend API (Semana 3-4)
1. **Lambda Functions**
   ```python
   import json
   import boto3
   
   def lambda_handler(event, context):
       # Função para buscar produtos
       dynamodb = boto3.resource('dynamodb')
       table = dynamodb.Table('products')
       
       response = table.scan()
       items = response['Items']
       
       return {
           'statusCode': 200,
           'body': json.dumps(items),
           'headers': {
               'Content-Type': 'application/json',
               'Access-Control-Allow-Origin': '*'
           }
       }
   ```

2. **API Gateway Configuration**
   - Endpoints RESTful
   - Autenticação JWT
   - Rate limiting
   - CORS configuration

### Fase 4: Frontend (Semana 4-5)
1. **Aplicação React/Vue.js**
   ```javascript
   // Integração com API
   const fetchProducts = async () => {
     const response = await fetch(
       'https://api.farmacia.com/products'
     );
     return response.json();
   };
   ```

2. **Deploy no S3 + CloudFront**
   ```bash
   # Build da aplicação
   npm run build
   
   # Sync com S3
   aws s3 sync ./dist s3://farmacia-frontend-bucket
   
   # Invalidação do CloudFront
   aws cloudfront create-invalidation \
     --distribution-id E1234567890 \
     --paths "/*"
   ```

### Fase 5: Segurança e Conformidade (Semana 5-6)
1. **Implementação LGPD/GDPR**
   - Criptografia de dados sensíveis
   - Políticas de retenção
   - Logs de consentimento

2. **WAF Rules**
   ```json
   {
     "Name": "PharmacyProtection",
     "Rules": [
       {
         "Name": "SQLInjectionRule",
         "Statement": {
           "SqliMatchStatement": {
             "FieldToMatch": {
               "AllQueryArguments": {}
             },
             "TextTransformations": [
               {
                 "Type": "URL_DECODE",
                 "Priority": 1
               }
             ]
           }
         },
         "Action": {
           "Block": {}
         }
       }
     ]
   }
   ```

## 📊 Monitoramento e DevOps

### CloudWatch Dashboards
- Métricas de performance da aplicação
- Monitoramento de custos
- Alertas de segurança
- Health checks automatizados

### CI/CD Pipeline
```yaml
# CodePipeline configuration
version: 0.2
phases:
  install:
    runtime-versions:
      nodejs: 14
  pre_build:
    commands:
      - npm install
  build:
    commands:
      - npm run build
      - npm run test
  post_build:
    commands:
      - aws s3 sync dist/ s3://$S3_BUCKET/
```

## 💰 Gestão de Custos

### Estimativa Mensal (Ambiente de Desenvolvimento)
- **EC2** (t3.micro): $8/mês
- **RDS** (db.t3.micro): $15/mês
- **S3** + **CloudFront**: $5/mês
- **Lambda**: $2/mês (baseado em uso)
- **API Gateway**: $3/mês
- **Total Estimado**: ~$35/mês

### Otimizações de Custo
- Reserved Instances para EC2/RDS
- S3 Intelligent Tiering
- CloudWatch Logs retention policies
- Auto Scaling Groups

## 🔒 Considerações de Segurança

### Dados Sensíveis
- Criptografia em trânsito e repouso
- Tokenização de dados de cartão
- Logs de auditoria completos
- Backup criptografado

### Conformidade Regulatória
- LGPD compliance
- Certificação PCI DSS
- Políticas de acesso médico
- Rastreabilidade de prescrições

## 📈 Métricas de Sucesso

- **Performance**: Tempo de resposta < 200ms
- **Disponibilidade**: SLA 99.9%
- **Segurança**: Zero incidentes críticos
- **Escalabilidade**: Suporte a 10k usuários simultâneos
- **Custo**: Otimização de 20% nos primeiros 6 meses

## 🚀 Próximos Passos

1. **Implementação Mobile**
   - AWS Amplify para app nativo
   - Push notifications com SNS

2. **Machine Learning**
   - Recomendações personalizadas com SageMaker
   - Detecção de fraudes automática

3. **IoT Integration**
   - Sensores de temperatura para medicamentos
   - Rastreamento em tempo real

## 📚 Recursos de Aprendizado

### Documentação AWS
- [AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected/)
- [AWS Security Best Practices](https://aws.amazon.com/security/security-learning/)
- [AWS Cost Optimization](https://aws.amazon.com/aws-cost-management/)

### Cursos Recomendados
- AWS Cloud Practitioner
- AWS Solutions Architect Associate
- AWS Developer Associate

---

**Anexos:**
- Detalhamento técnico da arquitetura implementada
- Cronograma de migração por etapas
- Análise comparativa de custos (antes vs depois)
- Métricas de performance e disponibilidade

---

*Relatório elaborado em conformidade com as diretrizes de implementação de cloud computing da Abstergo Industries por Anthony Mahyhaker Silva.*