# AWS_CloudFormation
🟢 O que é o AWS CloudFormation

O AWS CloudFormation é um serviço que permite criar, configurar e gerenciar recursos da AWS automaticamente por meio de modelos (templates) escritos em YAML ou JSON.

💡 Em vez de criar recursos manualmente (EC2, VPC, S3, RDS etc.) pelo console, você descreve tudo em um arquivo de configuração — e o CloudFormation provisiona automaticamente tudo pra você.

🔹 Exemplo simples:

Um modelo CloudFormation pode descrever algo assim:

Resources:
  MinhaInstanciaEC2:
    Type: AWS::EC2::Instance
    Properties:
      InstanceType: t2.micro
      ImageId: ami-0abcdef12345


Esse código cria uma instância EC2 automaticamente, sem precisar clicar no console.

🎯 Principais benefícios:

Automação da criação de recursos.

Padronização de ambientes (dev, teste, produção).

Reprodutibilidade: você pode recriar a mesma infraestrutura várias vezes.

Controle de versão: os templates podem ser armazenados no Git.

Infraestrutura como código (IaC) — o CloudFormation é a ferramenta nativa da AWS para isso.

🟢 Criando Stacks no AWS CloudFormation

Quando você envia um template para o CloudFormation, ele cria uma Stack (pilha).
➡️ Uma Stack é o conjunto de recursos que o CloudFormation cria e gerencia como uma unidade única.

🔹 Exemplo prático:

Você cria uma Stack chamada “StackWebApp”, e o template define:

1 instância EC2

1 bucket S3

1 grupo de segurança

Quando você executa a Stack:

O CloudFormation cria todos esses recursos automaticamente.

Se você excluir a Stack, todos os recursos associados também são removidos.

📦 Ou seja, a Stack é como uma “caixa” que agrupa os recursos criados a partir de um template.

🟢 Criando Stacks de Firewall no CloudFormation

Esse é um exemplo mais específico de uso.
Você pode usar o CloudFormation para provisionar automaticamente recursos de segurança, como AWS Network Firewall, Security Groups, NACLs (Network ACLs) e VPCs.

🔹 Exemplo:

Um template pode criar automaticamente:

Uma VPC com sub-redes públicas e privadas,

Um Firewall dentro dessa VPC,

E as regras de segurança configuradas.

Assim, você garante que todas as suas aplicações novas terão a mesma configuração de segurança, sem erros manuais.

🧩 Resumo geral
Conceito	Descrição	Exemplo
CloudFormation	Serviço IaC da AWS para automatizar criação de recursos	Criar instância EC2 via template
Template	Arquivo YAML/JSON que descreve os recursos	“Receita” da infraestrutura
Stack	Conjunto de recursos criados a partir de um template	Pilha com EC2 + S3 + SG
Stack de Firewall	Modelo pronto com regras de rede e segurança	VPC com Firewall e sub-redes
Infraestrutura como Código (IaC)	Gerenciar recursos AWS como código	Versionar no Git e automatizar deploys

✅ Resumo final:

O AWS CloudFormation permite criar e gerenciar toda a sua infraestrutura AWS como código, de forma automatizada, segura e reproduzível.

As Stacks são os conjuntos de recursos criados a partir de um template, e você pode usar isso para tudo — desde criar uma simples instância EC2 até infraestruturas completas com firewall, redes e bancos de dados.
