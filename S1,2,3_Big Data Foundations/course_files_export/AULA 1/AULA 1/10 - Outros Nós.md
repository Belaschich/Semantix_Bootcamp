# Outros nós

## Secundary Node

### NameNode
Responsável por armazenar todos os metadados dos nós do cluster.

Dentro do NameNode existem dois arquivos:
- FsImage

Armazena informações estruturais dos blocos

- Editlog

Armazena todas as informações ocorridas nos metadados dos arquivos

```Com esses dois arquivos é possível saber onde os arquivos estão e quais mudaram sofreram.```

### fsImage.ckpt

- São checkpoint criados no NameNode
- Esse arquivo é a junção do FsImage e do Editlog
- O checkpoint é criado após cada job

```Quando ocorre alguma falha no NameNode é preciso recuperar os dados no NameNode secundário através do arquivo fsImage.ckpt.```

**OBS:** o Secundary Node é mais usado é ambientes de desenvolvimento, em produção é mais comum usar o Standby NameNode.

# Standby NameNome

- Também é um NameNode, porém não está ativo, está em espera
- Ele se comunica com o NameNode ativo através de pacotes chamados JournalNodes
- Caso o NameNode ativo tenha falha o Standby assume seu lugar
- Isso acontece porque todos os DataNodes se comunicam tanto com o NameNode ativo quanto com o Standby NameNode
- Então quando o ativo falha, o Standby já está disponível para assumir
- Essa estratégia é boa porque não exige recuperação manual dos dados, dessa forma os dados não se perdem
- Por isso é muito importante em um ambiente de produção

# Edge Node

- Também pode ser chamado de Gateway Node por alguns autores
- Esse nó é a interface entre o cluster do Hadoop e a rede externa
- Esse Node Não faz parte do Cluster Hadoop, ele está fora do Cluster, mas faz a comunicação entre o cliente e o Cluster;
- Isso aumenta a segurança do cluster e reduz o uso de recursos do NameNode
- Por isso que o Edge Node é de extrema importância, permitindo a execução dos aplicativos nesse nó, o NameNode pode ficar focado apenas em armazenar e utilizar os metadados dos DataNodes para comandar as operações do Cluster Hadoop
- Várias ferramentas de gerenciamento são instaladas no Edge Node, por exemplo: Sqoop, Hive, Hue, entre outras.







