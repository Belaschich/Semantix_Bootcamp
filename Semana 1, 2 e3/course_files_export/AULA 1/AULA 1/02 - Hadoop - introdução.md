# HADOOP

Software open-source para computação distribuída confiável e escalável.

Propõe soluções para sistemas distribuídos em um único framework.

## Características

- Modelo de programação simples: comandos linux e SQL
- Processamento distribuído: vários nós (nó é como chamamos cada máquina em um cluster de computadores)
- Arquitetura pensada para big data
-  Clusters de computadores: arquitetura pensada em hardware de falha.

## Funcionamento

- Implementa um novo paradigma chamada Map/Reduce:
- Fornece um sistema de arquivos distribuídos (HDFS)  

### MapReduce:

Responsável pelo processamento dos dados no Hadoop.

- Aplicação é dividida em vários pequenos fragmentos (jobs)
- Cada job pode ser executado ou reexecutado em qualquer nó do cluster.

### HDFS  

Armazena dados nos nós.

- Fornece uma largura de banda muito alta em todo o cluster (que utiliza map/reduce)
- O HDFS foi projetado para em caso de falha em algum nó haver reprocessamento automático.

**OBS:** devido a esse reprocessamento não é necessário a existência de máquinas com alta garantia de disponibilidade ou inexistência de falhas.