# ✅ Solução — Desafio DevOps #01 — Criar EC2 com Terraform (Nível Intermediário)

Parabéns por avançar mais uma etapa do desafio!  
Este arquivo descreve os passos necessários para concluir o desafio intermediário e detalha todas as melhorias implementadas em relação ao desafio iniciante.

O objetivo deste nível foi evoluir um projeto Terraform básico, aplicando práticas mais profissionais e preparando o terreno para desafios mais avançados.

## 🎯 O que foi implementado nesta solução?

Esta solução inclui todas as melhorias solicitadas no desafio intermediário:

### ✔ 1. Modularização do projeto

A infraestrutura foi separada em módulos dentro de:

```
modules/
ec2/
security_group/
iam/
```

Cada módulo possui:

- `main.tf`
- `variables.tf`
- `outputs.tf`

Isso torna o código mais organizado, reutilizável e fácil de manter.

### ✔ 2. Uso de `tfvars`

Foi criado o arquivo:

```
dev.tfvars
```

Usado para controlar variáveis como:

- ambiente (`environment`)
- nome da instância
- nome do SG
- tipo de SO para a AMI
- habilitar/desabilitar o módulo IAM

Isso permite separar configurações por ambiente (dev, prod, etc.).

### ✔ 3. AMI dinâmica via data source

A AMI não é mais definida manualmente. Agora:

```hcl
data "aws_ami" "selected" {
  owners = ["amazon"]

  filter {
    name   = "name"
    values = ["${var.os_type}-ami-*"]
  }

  most_recent = true
}
```

Isso garante que a instância sempre use uma AMI atual e compatível com o sistema operacional escolhido.

### ✔ 4. Módulo IAM opcional

Foi criado um módulo IAM completo contendo:

* IAM Role
* IAM Policy (com permissões de leitura para RDS)
* Instance Profile

E a EC2 usa a role **apenas se `enable_iam = true`** no `tfvars`.

### ✔ 5. Organização e boas práticas

Inclui:

* `main.tf` limpo e somente com chamadas para módulos
* Variáveis centralizadas e documentadas
* Mais outputs
* Tags consistentes

## ▶️ Como executar esta solução

```
cd solucao
terraform init
terraform apply -var-file="dev.tfvars"
```

Após o apply, abra no navegador:

```
http://<IP_PUBLICO_OUTPUT>
```

Você verá a página criada pelo User Data.

## 🧹 Como destruir a infraestrutura

```
terraform destroy -var-file="dev.tfvars"
```

## 🧠 Pontos importantes para estudar após analisar a solução

* Reutilização de módulos em projetos maiores
* Criar módulos públicos ou privados (Terraform Registry)
* Backend remoto (S3 + DynamoDB) → será usado no nível avançado
* GitHub Actions para CI/CD de Terraform
* Workspaces e múltiplos ambientes
* Estrutura de pastas para projetos grandes

## 🔜 Próximos Passos

Se você concluiu este desafio e revisou a solução, o próximo passo é avançar para:

➡️ [**Desafio DevOps #01 — Nível Avançado**](https://github.com/bfeliano/desafio-devops-01-terraform-ec2-avancado)   

Nele você irá elevar ainda mais o projeto desenvolvido nos níveis iniciante e intermediário, implementando melhorias como:

- Configuração de backend remoto em S3 para armazenamento do estado
- Organização do projeto com states separados para cada ambiente (ex.: dev e prod)
- Implementação de CI/CD com GitHub Actions, garantindo validação automática (fmt, validate, plan)
- Integração de TFLint para aplicar linting e boas práticas
- Detecção e prevenção de drift, assegurando que o estado reflita a infraestrutura real
- Organização mais profissional de arquivos e ambientes, refletindo padrões utilizados em equipes Cloud/DevOps modernas
 
E parabéns por chegar até aqui — agora você já está pronto(a) para o **Desafio Avançado**. 🚀🔥