# Estrutura do MapReduce1

O MapReduce é executado por daemons, ou seja, em segundo plano, são eles: **JobTracker** e **TaskTracker**.

## JobTracker
- Existe apenas um
- É o principal daemon do MapReduce
- É um daemon que coordena todas as tarefas executadas no sistema;

### Funções:
- Agenda execução de tarefas em TaskTrackers
- Monitora as TaskTrackers, para reagendar em caso de falha ou execução lenta
- Armazena o histórico das tarefas concluídas

## TaskTracker
- Existem vários
- Executam as tarefas
- Enviam relatórios das tarefas para o JobTracker

### Funcionamento

- O JobTracker recebe a requisição do cliente
- O JobTracker envia a requisição para o TaskTracker menos ocupado
- O TaskTracker retorna relatórios de processamento para o JobTracker
- Ao fim do processo o TaskTracker retorna o relatório indicando fim da tarefa
- Caso haja falha no processo o TaskTracker retorna relatório indicando falha na tarefa
- Nesse caso o JobTracker reencaminha a tarefa para ser executada por outro TaskTracker em outro nó do cluster.

**OBS:** caso uma tarefa esteja muito lenta o JobTracker pode parar o processo e redirecionar para ser executado por outro TaskTracker em outro nó do cluster.


