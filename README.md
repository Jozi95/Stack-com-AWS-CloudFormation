# Meu Primeiro Projeto com AWS CloudFormation

## 1. Introdução
Neste projeto, meu objetivo foi **aprender a criar minha primeira Stack na AWS utilizando CloudFormation**. Durante a prática, explorei recursos como **EC2, S3 e Security Groups**, aplicando os conceitos que aprendi nas aulas da DIO.

> Aqui você pode adicionar mais sobre sua motivação pessoal, expectativas ou contexto do projeto.

---

## 2. Tecnologias Utilizadas
- **AWS CloudFormation**  
- **AWS CLI**  
- **Git/GitHub**  
- **VS Code** (para editar arquivos YAML e scripts)  
- **Markdown** (para documentação)  

> Adicione outras ferramentas se utilizou, como terminal, extensões do VS Code, ou scripts adicionais.

---

## 3. Passo a Passo da Implementação

### 3.1 Preparação
Antes de criar a Stack, realizei os seguintes passos:
- Assisti todas as aulas do módulo.  
- Baixei e explorei o material complementar fornecido pelo curso.  
- Revisei a documentação oficial da AWS CloudFormation.

---

### 3.2 Criação do Template
Criei um arquivo `template.yaml` contendo os recursos que queria provisionar:  
- **S3 Bucket** para armazenar arquivos  
- **Security Group** para liberar acesso SSH e HTTP  
- **EC2 Instance** conectada ao Security Group  

Exemplo de template (resumido):

```yaml
Resources:
  MeuBucket:
    Type: AWS::S3::Bucket
    Properties:
      BucketName: meu-primeiro-bucket-dio-2025

  MeuSG:
    Type: AWS::EC2::SecurityGroup
    Properties:
      GroupName: meu-primeiro-sg
      GroupDescription: Security Group criado com CloudFormation
      SecurityGroupIngress:
        - IpProtocol: tcp
          FromPort: 22
          ToPort: 22
          CidrIp: 0.0.0.0/0
        - IpProtocol: tcp
          FromPort: 80
          ToPort: 80
          CidrIp: 0.0.0.0/0

  MinhaEC2:
    Type: AWS::EC2::Instance
    Properties:
      InstanceType: t2.micro
      KeyName: MINHA_KEY_PAIR
      ImageId: ami-0c55b159cbfafe1f0
      SecurityGroupIds:
        - !Ref MeuSG
# Stack-com-AWS-CloudFormation
Neste projeto, meu objetivo foi **aprender a criar minha primeira Stack na AWS utilizando CloudFormation**. Durante a prática, explorei recursos como **EC2, S3 e Security Groups**, aplicando os conceitos que aprendi nas aulas da DIO.
