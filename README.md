# Curso Full Cycle 3.0 - Módulo Deploy nas Cloud Providers (AWS)

<div>
    <img alt="Criado por Alcir Junior [Caju]" src="https://img.shields.io/badge/criado%20por-Alcir Junior [Caju]-%23f08700">
    <img alt="License" src="https://img.shields.io/badge/license-MIT-%23f08700">
</div>

---

## Descrição

O Curso Full Cycle é uma formação completa para fazer com que pessoas desenvolvedoras sejam capazes de trabalhar em projetos expressivos sendo capazes de desenvolver aplicações de grande porte utilizando de boas práticas de desenvolvimento.

---

## Repositório Pai
https://github.com/alcir-junior-caju/study-full-cycle-3-0

---

## Visualizar o projeto na IDE:
Para quem quiser visualizar o projeto na IDE clique no teclado a tecla `ponto`, esse recurso do GitHub é bem bacana

---

### O que é computação em nuvem?

Computação em nuvem é o uso e fornecimento de recursos computacionais como armazenamento, processamento, serviços para execução de aplicações e até soluções completas de software de forma remota pela internet.

### Vantagens de computação em nuvem
- Consumo por demanda;
- Otimização de custo;
- Velocidade de aquisição;
- Distribuição global;
- Escala;
- Simplicidade de gerenciamento;

### Tipos de serviços
@ Gerenciado por você.

& Gerenciado pelo Cloud Provider.

- On Premisse;
    - @Aplicação;
    - @Dados;
    - @Runtime;
    - @Middleware;
    - @Sistema Operacional;
    - @Virtualização;
    - @Servidores;
    - @Armazenamento;
    - @Rede;
- Infraestrutura como serviço;
    - @Aplicação;
    - @Dados;
    - @Runtime;
    - @Middleware;
    - @Sistema Operacional;
    - &Virtualização;
    - &Servidores;
    - &Armazenamento;
    - &Rede;
- Plataforma como serviço;
    - @Aplicação;
    - @Dados;
    - &Runtime;
    - &Middleware;
    - &Sistema Operacional;
    - &Virtualização;
    - &Servidores;
    - &Armazenamento;
    - &Rede;
- Software como serviço;
    - &Aplicação;
    - &Dados;
    - &Runtime;
    - &Middleware;
    - &Sistema Operacional;
    - &Virtualização;
    - &Servidores;
    - &Armazenamento;
    - &Rede;

### AWS (Amazon Web Services)
- Criada em 2006;
- Surgiu com a ideia de utilizar a sua infra interna como serviço para clientes;
- Hoje possuí mais de 200 serviços disponíveis para uso;
- Distribuição global;

### Região
Região é uma área do mundo onde existe uma Infraestrutura.

### Zona de disponibilidade
É o Datacenter, a Infraestrutura, e sempre vai ter mais de uma zona de disponibilidade em cada região, onde a distância mínima é de pelo menos 100 kilometros e todas elas se conectam entre si.

### Zona Local
São pequenos locais de Infraestrutura da AWS, onde se diminui a distancia das Zonas de disponibilidades, com isso a latência diminui. Não so todas Regiões que possuem zona local e não são todos os serviços disponíveis.

### Wavelength
É utilizado em soluções que utilizamo dados móveis, então existe uma Infraestrutura da AWS dentro da operadora, assim a latência é menor. E também não estão disponíveis em todas regiões.

[Link Infra AWS](https://aws.amazon.com/pt/about-aws/global-infrastructure/regions_az/)

### IAM (Indentity Access Manager)
- User;
- Groups;
- Role;
    - São permissões vinculadas a serviços;
- Policy;
    - Objeto que define os acessos da AWS;
    - Uma policy pode ser vinculada a um User, Group ou Role;
    - A construção de uma policy é utilizado JSON;
    - Você pode utilizar policies já existentes ou criar as suas;
    - Para definir um recurso, se usa o ARN (Amazon Resource Names), todo recurso na AWS gera um ARN;
        - Exemplos:
            - arn:partition:service:region:account-id:resource-id;
            - arn:partition:service:region:account-id:resource-type/resource-id;
            - arn:partition:service:region:account-id:resource-type:resource-id;
        - Partition: Representa em qual grupo de regiões a conta pertence. Hoje existem as seguintes regiões:
            - aws: Regiões da AWS;
            - aws-cn: Regiões da China;
            - aws-us-gov: Regiões Gov da AWS;
        - Service: Nome do serviço que identifica o produto da AWS;
        - Region: Código da região;
        - Account-ID: O ID da sua conta na AWS;
        - Resource-Type: O tipo de recurso;
        - Resource-ID: Esse é o nome do recurso. Alguns recursos incluem o recurso pai no formato, exemplo:
            - recurso pai: sub-resource-type/parent-resource/sub-resource;
            - versão: resource-type:resource-name:qualifier;
        - Exemplos:
            - arn:aws:iam::123123123:user/jhondoe;
            - arn:aws:ec2:us-east-1:123123123:vpc/vpc-0e789798EXAMPLE;
            - arn:aws:iam::123123123:user/*;
            - arn:aws:iam::123123123:group/*;

### EC2 (Elastic Compute Cloud)
- Foi um dos primeiros serviços criado pela AWS;
- Permite a criação de máquinas Windows, Linux e Mac;
- Suporte a arquitetura 64 bits x86 ou 64 bits Arm;
- A cobrança de um EC2 é feita por segundo. Mas você deve ter um consumo mínimo de 60 segundos;
- Pode criar máquinas com acesso público ou não;

#### Tipo de EC2
- Uso Geral: São instâncias com mais equilíbrio entre CPU, memória e rede. São os tipos mais usados e servem para um uso mais abrangente;
- Otimizadas para computação: São instâncias que tem como foco o uso de CPU. São usados em tarefas de alto processamento;
- Otimizadas para memória: São instâncias que tem como foco o uso de memória RAM. São usados em tarefas que possuem maior consumo de memória RAM;
- Computação acelerada: São usadas para cenários de processamento gráfico ou cálculos de números flutuantes. Tem maior foco no uso de GPU;
- Otimizadas para armazenamento: São usadas para cargas que exigem alto acesso a leitura e gravação;
- Otimizadas para alta performance: São usadas para computação de alta performance, como simulações complexas e cargas com aprendizado profundo;

[Link tipos](https://aws.amazon.com/pt/ec2/instance-types)

### VPC
- Toda vez que criar uma VPC, vai ser definido uma região;
- As VPCs não se comunicam entre si;
- Pode se criar subnet para VPC;
- Toda subnet é vinculada a uma zona de disponibilidade;
- Siderblock:
    - 10.35.65.87 / 10.35.0.0/16 = 00000000.00000000.00000000.00000000
    - o /16 = informa que os 16 primeirs bits vão representar endereçamento de rede;
    - 10.35 = endereçamento de rede;
    - 65.87 = dispositivos;
- Subnet publica: tem acesso a internet;
- Subnet privada: não tem acesso a internet;
- Para ativar a internet:
    - Na VPC, precisa criar um Internet Gateway e fazer o Attach para liberar o acesso a internet;
    - Na VPC, precisa criar um Route Table, e vincular a VPC, após criada é necessário fazer as associações as subnets, após associar é necessário criar as regras de rotas:
        - É necessário adicionar as rotas com Destination e target, exemplo: Destination: 0.0.0.0/0 - Target: Internet Gateway criado;
    - Bastion Host: é necessário copiar a chave para EC2 privada para ter acesso a partir da pública;
    - Nat Gateway: Serve para dar acesso a internet a EC2 privada:
        - Se cria uma Nat Gateway na EC2 pública e vincular a EC2 privada;

[Link subnet calculator](https://mxtoolbox.com/subnetcalculator.aspx)

### Scurity Group
- É sempre vinculado a uma instância;
- Regras de Inbound (Entrada);
- Regras de Outbound (Saída);
