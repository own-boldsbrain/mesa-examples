# Modelo de Reservas Bancárias

## Resumo

Um modelo altamente abstraído e simplificado de uma economia, com apenas um tipo de agente e um único banco representando todos os bancos de uma economia. As pessoas (representadas por círculos) se movem aleatoriamente dentro da grade. Se duas ou mais pessoas estiverem na mesma localização da grade, há uma chance de 50% de que elas negociem entre si. Se negociarem, há uma chance igual de dar ao outro agente $5 ou $2. Um saldo comercial positivo será depositado no banco como poupança. Se a negociação resultar em um saldo negativo, o agente tentará sacar de sua poupança para cobrir o saldo. Se não tiver poupança suficiente para cobrir o saldo negativo, ele fará um empréstimo no banco para cobrir a diferença. O banco é obrigado a manter uma certa porcentagem dos depósitos como reservas. Se o arquivo run.py for usado para executar o modelo, a porcentagem de depósitos que o banco é obrigado a reter é um parâmetro ajustável pelo usuário. O montante que o banco pode emprestar em um determinado momento é uma função do montante de depósitos, suas reservas e o valor total atual de empréstimos pendentes.

O modelo demonstra os seguintes recursos do Mesa:

- MultiGrid para criar espaço compartilhável para agentes
- DataCollector para coletar dados de execuções individuais do modelo
- Slider para ajustar os parâmetros iniciais do modelo
- ModularServer para visualização da interação dos agentes
- Herança de objetos Agent
- Uso de um BatchRunner para coletar dados sobre múltiplas combinações de parâmetros do modelo

## Instalação

Para instalar as dependências, use o pip e o arquivo requirements.txt neste diretório. Por exemplo:

```bash
pip install -r requirements.txt
```

## Execução Interativa do Modelo

Para executar o modelo interativamente, use `mesa runserver` neste diretório:

```bash
mesa runserver
```

Em seguida, abra seu navegador em [http://127.0.0.1:8521/](http://127.0.0.1:8521/), selecione os parâmetros do modelo, pressione Reset e depois Start.

## Execução em Lote

Para executar o modelo como uma execução em lote para coletar dados sobre múltiplas combinações de parâmetros do modelo, execute "batch_run.py" neste diretório.

```bash
python batch_run.py
```

Uma barra de status de progresso será exibida.

Para atualizar os parâmetros e testar outras varreduras de parâmetros, edite a lista de parâmetros no dicionário chamado "br_params" em "batch_run.py".

## Arquivos Principais

- ``run.py``: Inicia um servidor de visualização do modelo.
- ``batch_run.py``: Basicamente o mesmo que model.py, mas inclui um Mesa BatchRunner. O resultado da execução em lote será um arquivo .csv com os dados de cada passo de cada execução.

## Leitura Adicional

Este modelo é uma implementação em Mesa do modelo de Reservas Bancárias do NetLogo:

Wilensky, U. (1998). Modelo de Reservas Bancárias NetLogo. http://ccl.northwestern.edu/netlogo/models/BankReserves. Center for Connected Learning and Computer-Based Modeling, Northwestern University, Evanston, IL.

