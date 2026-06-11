# Gerenciamento de Instâncias EC2, AMIs e Snapshots na AWS 🚀

Este repositório foi desenvolvido para o desafio de projeto da Formação AWS na DIO (Digital Innovation One). O objetivo é documentar as boas práticas e o fluxo de trabalho para provisionamento e backup de servidores virtuais (IaaS) utilizando a nuvem da AWS.

---

## 📌 Escopo do Laboratório Técnico

O projeto consiste no planejamento de uma infraestrutura resiliente baseada no Amazon EC2, mapeando o ciclo de vida de servidores e suas respectivas estratégias de recuperação de desastres.

### 1. Provisionamento do Amazon EC2
- **Instância:** Configuração teórica de uma instância `t2.micro` (elegível ao AWS Free Tier).
- **Sistema Operacional:** Ubuntu Server 24.04 LTS.
- **Segurança:** Definição de regras de firewall via *Security Groups*, liberando apenas as portas estritas para a aplicação (Porta 22 para SSH administrativo e Porta 80/443 para tráfego Web).

### 2. Estratégia de Backup com EBS Snapshots
- **O que é:** O Snapshot do Amazon EBS (Elastic Block Store) é um backup incremental a nível de bloco do disco rígido da instância.
- **Aplicação Prática:** Utilizado para salvar o estado dos dados do disco em um determinado momento. Caso ocorra uma corrupção de arquivos, um novo volume pode ser criado a partir deste Snapshot em poucos segundos.

### 3. Escalabilidade e Imagens Customizadas (AMIs)
- **O que é:** A Amazon Machine Image (AMI) é o molde completo da máquina virtual (incluindo sistema operacional, configurações, ferramentas instaladas e ponteiros para os discos).
- **Aplicação Prática:** Essencial para estratégias de *Auto Scaling* e recuperação de desastres global. Com a AMI gerada a partir do servidor base, é possível clonar a máquina idêntica em qualquer outra Zona de Disponibilidade da AWS instantaneamente.

---

## 🧠 Insights e Aprendizados Adquiridos

- **Arquitetura Descentralizada:** Compreendi que manter snapshots regulares é vital para a tolerância a falhas de dados, enquanto a criação de AMIs é voltada para a padronização e escalabilidade da aplicação.
- **Ambiente Local vs Nuvem:** Durante a concepção do projeto, foi avaliada a viabilidade do uso de ferramentas como o *LocalStack* para simulação de serviços AWS em ambientes de desenvolvimento local, reduzindo custos de desenvolvimento e acelerando testes de infraestrutura antes do deploy em produção.

---
⚙️ Desenvolvido para fins educacionais na plataforma DIO.
