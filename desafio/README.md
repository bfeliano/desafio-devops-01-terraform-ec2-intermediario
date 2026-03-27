# 🧩 Desafio DevOps #01 — Criar EC2 com Terraform (Nível Intermediário)

Bem-vindo(a) ao segundo nível do Desafio DevOps #01!  
Aqui você irá evoluir a solução criada no nível iniciante, aplicando práticas mais avançadas de **Infraestrutura como Código** utilizando **Terraform**.

Este desafio é ideal para quem já concluiu o nível iniciante e agora deseja aprender a estruturar projetos Terraform de maneira mais profissional e escalável.

## 🎯 Objetivo

Dentro desta pasta (`/desafio`), você encontrará a **base completa** construída no desafio iniciante.  

A partir dessa base, o objetivo é aprimorar o projeto implementando melhorias como:

1. Refatorar o código usando **módulos Terraform**
2. Utilizar arquivos **`.tfvars`** para facilitar customização
3. Criar **variáveis extras** e tornar o código mais flexível
4. Implementar uma **AMI dinâmica**, usando data sources
5. (Opcional) Criar uma **IAM Role e Instance Profile** para a instância EC2
6. Melhorar organização, tags, outputs e boas práticas gerais

A ideia aqui não é apenas “fazer funcionar”, mas sim **evoluir o design do código**, criando uma estrutura mais limpa, separada e reutilizável.

Você já tem um projeto funcionando — agora é hora de transformá‑lo em algo mais robusto.

# 💬 Dicas importantes para te ajudar

## 💡 1. Separe sua infraestrutura em módulos

Considere criar uma estrutura como:

```
modules/
ec2/
security\_group/
iam/        (opcional)
```

Cada módulo deve ter seu próprio `main.tf`, `variables.tf` e `outputs.tf`.

## 💡 2. Utilize arquivos `.tfvars`

Crie arquivos como:

```
dev.tfvars
prod.tfvars
```

Exemplo de execução:

```
terraform apply -var-file="dev.tfvars"

```

Isso ajuda a manter ambientes diferentes de forma organizada.

## 💡 3. Adicione variáveis para tornar o código flexível

Algumas sugestões:

- Nome da instância  
- Nome do Security Group  
- Tags básicas (owner, environment)  
- Tipo de sistema operacional para AMI (ex.: `amazon-linux-2`)  

Evite valores fixos espalhados no código.

## 💡 4. Use data sources para selecionar automaticamente a AMI

Em vez de colocar o AMI ID manualmente, utilize:

```
data "aws_ami" "amzlnx2" {
...
}
```

Isso torna seu código mais confiável e portátil entre regiões.

## 💡 5. (Opcional) Crie uma IAM Role e Instance Profile

Isso aproxima o projeto do que é usado em ambientes reais.

Considere:

- `aws_iam_role`
- `aws_iam_policy`
- `aws_iam_instance_profile`

## 💡 6. Organize arquivos e outputs

O código deve continuar fácil de entender e de manter.

Algumas sugestões:

- `main.tf` enxuto, chamando apenas módulos
- Variáveis organizadas em `variables.tf`

## 💡 7. Teste em pequenas partes
Antes de rodar o `terraform apply`, execute:

```
terraform init
terraform fmt
terraform validate
```

Isso evita erros simples.

# 📁 Estrutura desta pasta

```
/desafio
├── main.tf                ← Base do desafio iniciante (para refatorar)
├── variables.tf           ← Você pode ajustar ou expandir
├── outputs.tf             ← Ajuste conforme evolução
├── user_data.sh           ← Script existente (pode ser mantido)
└── README.md              ← Este arquivo
```

# ▶️ Como Rodar o Desafio

1. Abra o diretório:

```
cd desafio
```

2. Inicialize o Terraform:

```
terraform init
```

3. Valide o código:

```
terraform validate
```

4. Aplique usando seu arquivo tfvars:

```
terraform apply -var-file="dev.tfvars"
```

5. Abra o navegador e teste:

```
http://<IP-PUBLICO-OUTPUT>
```

Se tudo estiver correto, você verá a mensagem:

```
Desafio DevOps #1 Intermediário — Deploy realizado com sucesso!
```

# 🧹 Como destruir a infraestrutura

```
terraform destroy
```

# ❗ Quando consultar a solução?

Apenas depois que você tentar resolver sozinho(a).  
A solução completa está na pasta solucao.


Boa sorte e divirta-se aprendendo DevOps na prática! 🚀🔥