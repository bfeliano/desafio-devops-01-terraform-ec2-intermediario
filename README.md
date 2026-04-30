# 🧩 Desafio DevOps #01 — Criar EC2 com Terraform (Nível Intermediário)

Este é o segundo nível do **Desafio DevOps #01**, onde você irá evoluir o projeto criado no desafio iniciante.
O foco agora é aplicar **boas práticas** reais de Terraform, tornando a infraestrutura mais modular, organizada e configurável.

Neste desafio, você avançará o projeto implementando melhorias como:

- Uso de **módulos** Terraform
- Criação e utilização de **arquivos .tfvars**
- Adição de **variáveis extras** para personalização do ambiente
- Implementação de **AMI dinâmica** via **data source**
- (Opcional) inclusão de uma **IAM Role / Instance Profile** para a EC2

Este repositório segue o mesmo formato do nível iniciante:   
👉 a pasta **desafio/** contém os arquivos para você implementar  
👉 a pasta **solucao/** contém a implementação final

Prepare-se para elevar o nível da sua infraestrutura como código! ⚡

## 🤝 Participe da Comunidade

Tem dúvidas sobre o desafio ou quer compartilhar sua solução?  
Entre no nosso Discord oficial:

[![Discord](https://img.shields.io/badge/Discord-Desafios%20DevOps-5865F2?style=flat&logo=discord&logoColor=white)](https://discord.gg/RgcC7YytVZ)

Lá você encontrará fóruns por desafio, ajuda da comunidade e novidades sobre próximos desafios DevOps.

## 📁 Estrutura do Repositório

```
desafio-devops-01-terraform-ec2-intermediario/
│
├── desafio/       → Onde você deve desenvolver sua versão intermediária
├── solucao/       → Solução completa e modularizada
└── README.md      → Este arquivo
```

## 📌 Como completar o seu desafio?

Todo o desenvolvimento do seu código deve ser feito dentro da pasta:

```
/desafio
```
Nela você encontrará a base completa do projeto criado no desafio iniciante.  
A partir dessa base, você deve evoluir a infraestrutura aplicando boas práticas como módulos, tfvars, AMI dinâmica e outras melhorias descritas no README dessa pasta.

Quando terminar ou quiser comparar a sua abordagem, a solução final está disponível em:

```
/solucao
```

## 🛠️ Pré-requisitos

Antes de começar, instale:

- **Terraform**  
  https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli  
- **AWS CLI** configurado (`aws configure`)  
  Instalação: https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html  
  Configuração: https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html

Você deve possuir também uma **conta AWS** com permissões básicas de EC2 e VPC.

## 🔜 Próximos Passos

Este desafio faz parte de uma trilha contínua de aprendizado DevOps.

Depois de concluir este nível, você pode avançar para:

➡️ [**Desafio DevOps #01 — Nível Avançado**](https://github.com/bfeliano/desafio-devops-01-terraform-ec2-avancado)  
Nele você irá elevar ainda mais o projeto desenvolvido nos níveis iniciante e intermediário.

## 🤝 Contribuições

Pull requests com melhorias em documentação, estrutura ou sugestões para novos desafios são bem-vindos!

## 📄 Licença

Este projeto está sob a licença MIT. Consulte o arquivo `LICENSE` para mais detalhes.
