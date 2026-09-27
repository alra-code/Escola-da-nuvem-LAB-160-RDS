<div align="center">

# 🗄️ Lab 160 — Criando um Servidor de Banco de Dados com Amazon RDS

![RDS](https://img.shields.io/badge/AWS-RDS-FF9900?style=for-the-badge&logo=amazon-aws&logoColor=white)
![MySQL](https://img.shields.io/badge/Database-MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![High Availability](https://img.shields.io/badge/Multi--AZ-High_Availability-2E86C1?style=for-the-badge&logo=cloudscale&logoColor=white)
![Status](https://img.shields.io/badge/Status-Concluído-2ECC71?style=for-the-badge)

</div>

---

## 📌 Sobre o laboratório

Este laboratório foi criado para reforçar o conceito de utilização de uma **instância de banco de dados gerenciada pela AWS** para atender às necessidades de um banco de dados relacional.

> 💡 **Cenário:** evoluir uma arquitetura já existente (VPC + servidor web) adicionando uma camada de **banco de dados relacional gerenciado e altamente disponível**, integrada ao servidor web.

---

## 🎯 Objetivos

Ao concluir este laboratório, fui capaz de:

- 🗄️ Executar uma instância de banco de dados do **Amazon RDS com alta disponibilidade**
- 🔌 Configurar a instância de banco de dados para permitir **conexões do servidor web**
- 🌐 Abrir um **aplicativo web** e interagir com o banco de dados

---

## 🗺️ Arquitetura

### 🔹 Infraestrutura inicial

<img width="655" height="315" alt="Image" src="https://github.com/user-attachments/assets/49b1618b-8e2a-4f44-931d-a8f289531e40" />

### 🔹 Infraestrutura final (com RDS Multi-AZ)

<img width="657" height="315" alt="Image" src="https://github.com/user-attachments/assets/99a6eacb-7d64-42fd-ab12-e7bfb933dcf3" />


## 🛠️ Etapas realizadas

### ✅ Tarefa 1 — Criar um grupo de segurança para a instância de banco de dados do RDS

Criação de um **Security Group** dedicado ao banco de dados, liberando conexões apenas a partir do Security Group do servidor web — mantendo o banco isolado do tráfego direto da internet.

### ✅ Tarefa 2 — Criar um grupo de sub-redes de banco de dados

Criação de um **DB Subnet Group**, usado para informar ao RDS quais sub-redes (privadas, em diferentes Zonas de Disponibilidade) podem ser utilizadas pelo banco de dados — pré-requisito para o modo **Multi-AZ**.

### ✅ Tarefa 3 — Criar uma instância de banco de dados do Amazon RDS

Configuração e inicialização de uma instância de banco de dados **Multi-AZ do Amazon RDS para MySQL**, garantindo failover automático em caso de falha na instância primária.

| Configuração | Valor |
|:---|:---|
| 🧬 Engine | MySQL |
| 🌎 Implantação | Multi-AZ (Primary + Secondary) |
| 🔗 Endpoint | `lab-db.c95lvu09zxro.us-west-2.rds.amazonaws.com` |

### ✅ Tarefa 4 — Interagir com o seu banco de dados

Abertura do aplicativo web em execução no servidor, configurando-o para se conectar ao banco de dados RDS recém-criado e validando a integração de ponta a ponta.

---

## ✅ Resultado final

Aplicação web conectada com sucesso à instância RDS, completando a arquitetura: **VPC → Servidor Web (EC2) → Banco de Dados gerenciado (RDS Multi-AZ)**. 🎉

---

## 🧠 Principais aprendizados

- 🔹 Como isolar o banco de dados em **sub-redes privadas**, sem exposição direta à internet
- 🔹 Papel do **DB Subnet Group** na distribuição do banco entre Zonas de Disponibilidade
- 🔹 Benefícios do modo **Multi-AZ** para alta disponibilidade e failover automático
- 🔹 Como conectar uma aplicação web hospedada em EC2 a um banco de dados gerenciado
- 🔹 Vantagens do **Amazon RDS** frente à administração manual de um banco de dados (patching, backups, escalabilidade)

---

## 🏷️ Tecnologias e Serviços

![Amazon RDS](https://img.shields.io/badge/Amazon-RDS-232F3E?style=flat-square&logo=amazon-aws&logoColor=FF9900)
![Amazon EC2](https://img.shields.io/badge/Amazon-EC2-232F3E?style=flat-square&logo=amazon-aws&logoColor=FF9900)
![Amazon VPC](https://img.shields.io/badge/Amazon-VPC-232F3E?style=flat-square&logo=amazon-aws&logoColor=FF9900)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)

---

<div align="center">

📚 *Laboratório prático realizado como parte da trilha de estudos em Computação em Nuvem, com foco em transição de carreira para Engenharia de Dados.*

</div>
