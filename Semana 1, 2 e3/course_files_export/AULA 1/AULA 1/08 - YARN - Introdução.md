# YET ANOTHER RESOURCE NEGOTIATOR

- Assim como o JobTracker do MapReduce o YARN também faz o gerenciamento de jobs no cluster Hadoop.
- Oferece paralelismo das tarefas
  
Divide em daemons separadas as seguintes funcionalidades:

- Gerenciamento de recursos
- Agendamento
- Monitoramento

Portanto ao invés de todo o monitoramento ser feito pelo JobTracker do MapReduce no YARN existem vários daemons diferentes.

Isso ocorre porque o YARN é um framework de MapReduce, logo é a evolução do mesmo.

## Versões

Hadoop 1 e inferior:
- MapReduce 1

Hadoop 2:
- MapReduce 2 = MapReduce 1 + YARN

## Configurações do Cluster Hadoop

- Modo local (Standalone): local
- Modo pseudo distribuído: single node cluster, existe apenas um nó nesse cluster
- Modo totalmente distribuído: multi node cluster, mais comum em produção

## ESTRUTURA DO YARN

Existem 4 diferentes tipos de daemons:
- Resource Manager (RM)
- Aplication Master (AM)
- Timeline Server 
- Node Manager

Os 3 primeiros tem funções semelhantes ao JobTracker e o último se assemelha os TaskTracker.

**OBS:** essas 3 estruturas separadas que executam as funções do JobTracker permitem maior controle.

### Resource Manager (RM)
- Coordena todas as tarefas executadas no sistema
- Agenda as tarefas para serem executadas nos Node Managers

### Aplication Master (AM)
- Monitorar os Node Managers
- Reagenda em caso de falha
- Reagenda em caso de lentidão

### Timeline Server 
- Armazena o histórico do aplicativo
- É opcional, essa tarefa não precisa ser separada
- Pode ser feito através do RM

### Node Manager

- Executam as tarefas no cluster, assim como o TaskTracker no MapReduce
- Executam as tarefas em contêineres
- Enviam relatório do progresso das tarefas para o RM
