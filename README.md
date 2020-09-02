# Spark

É uma plataforma analítica unificada para o processamento de dados em larga escala. Ou seja, o Spark pode ser utlizado em vários use cases distintos sem precisar combinar ferramentas para resolver problemas diferentes. Em geral, o Apache Spark é utilizado em use case analítico:

<ul>
  <li>Preparar dados para nálise</li>
  <li>Criar modelos de ML</li>
  <li>Analisar dados em tempo real</li>
</ul>

Funcionamento Resumido
======================

Driver Program é o responsável por orquestra a execução do programa. É a função Main onde está toda a lógica de execução do código. Possui um tamanho de memória alocada então é importante ficar atento para que não haja estouro de meória.

Lembre-se que a finalidade é executar tarefas de forma distribuída, portanto, a arquitetura possui o SparkContext que faz a ponte entre o driver program e o ambiente de execução da tarefa. Isso permite a execução distribuída em outro local que são definidos pelos executors. Portanto, o spark context faz uma conexão entre o driver e os executors. Pode ser configurado no sparkcontext o quanto de memória a ser utilizado ou o número de executors que é a quantidade de threads alocadas.

Todas as operações serão traduzidas para um plano de execução lógico conhecido como Lineage que é bastante similar aos encontrados nos bancos de dados relacionais (load, filter, return). Conhecendo a sequência lógica, o Spark cria o DAG Scheduler que é a sequência lógica quebrada por estágios ou stages do inglês. Conhecido os stages então finalmente o consegue criar as tarefas que serão executadas (Task Schedule).

Os Worker Node onde estão os Executors são os responsáveis por executar as tarefas, parametrizadas no driver program, de forma distribuída. Como estamos falando de execução distribuída é muito comum ter mais de um worker node envolvido na resolução de problemas que fazem do Spark como solução. 

Portanto entre o driver program e os worker nodes existe um cluster manager que faz a gestão dos recursos: memória e CPU, alocados nos worker nodes. O cluster manager pode ser do próprio Spark ou ferramenta de outro fornecedor.



Road Map
========
<ul>
  <li>Instalando e montando ambiente no Linux</li>
  <li>Configurando Apache Spark</li>
  <li>Como funciona a consulta de dados no Apache Spark usando Spark Dataframe (workload de dados e ETL) + Scala</li>
  <li>Spark Streaming (dados em tempo real), MLIB (ML) e GraphX (processamento de gráficos) na prática</li>
  <li>Aplicar Map Reduce</li>
  <li>E mais...</li>
</ul>

Instalando e montando ambiente no Linux:
========================================
Instalando com PyPi<br>
<a href="https://pypi.org/project/pyspark/">PySpark</a> está disponível em pypi. Para instalar execute o seguinte comando via terminal: pip install pyspark. Dica: Por mais que seja estável, não instale a última versão!
