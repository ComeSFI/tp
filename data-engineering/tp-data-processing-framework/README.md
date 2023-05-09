# Practices - Data engineering

## TP - Data processing with Apache Spark
To process a large amount of data partitioned on a data lake, you can use data processing frameworks such as Apache Spark :
1. Read : https://spark.apache.org/docs/latest/sql-programming-guide.html

Some questions :
* What is Spark RDD API ?
* What is Spark Dataset API ?
* With which languages can you use Spark ? 
* Which data sources or data sinks can Spark work with ? 

1: RDD, Resilient Distributed Datasets, and Datasets are two of the APIs of Spark. An RDD is an immutable distributed collection of data, which is partitioned across several machines that in parallel operate on the data. Two types of operations are provided by the RDD API: transformation, operations creating a new RDD based on an already existing one, and actions, operations returning raw values from the actual dataset (non-RDD value).

2: Building on the RDD API, Spark Dataset API is a newer API that offers a more efficient way of working with both structured and semi-structured data. It is a higher-level API that is more like SQL with some similar operations like join(), groupBy() and select() for example.

3: Spark supports several programming languages including Scala, Java, Python, and R.

4: Spark is capable of working with various data sources and sinks, thanks to its unified API. This makes it highly adaptable and versatile. Some of the data sources that Spark can work with include JSON files, CSV files, Parquet files, Microsoft Excel, Apache Kafka, and Hadoop Distributed File System (HDFS).

Spark's unified API also enables it to work with a variety of data sinks, such as relational databases, NoSQL databases, data warehouses, cloud storage, local file systems and directories, and Hadoop Distributed File System (HDFS).

### Analyse data with Apache Spark and Scala 
One engineering team of your company created for you a TV News data stored as JSON inside the folder `data-news-json/`.

Your goal is to analyze it with your savoir-faire, enrich it with metadata, and store it as [a column-oriented format](https://parquet.apache.org/).

1. Look at `src/main/scala/com/github/polomarcus/main/Main.scala` and update the code 

**Important note:** As you work for a top-notch software company following world-class practices, and you care about your project quality, you'll write a test for every function you write.

You can see tests inside `src/test/scala/` and run them with `sbt test`

### How can you deploy your app to a cluster of machines ?
* https://spark.apache.org/docs/latest/cluster-overview.html

### Business Intelligence (BI)
How could use we Spark to display data on a BI tool such as [Metabase](https://www.metabase.com/) ?

Tips: https://github.com/polomarcus/television-news-analyser#spin-up-1-postgres-metabase-nginxand-load-data-to-pg

### Continuous build and test
**Pro Tips** : https://www.scala-sbt.org/1.x/docs/Running.html#Continuous+build+and+test

Make a command run when one or more source files change by prefixing the command with ~. For example, in sbt shell try:
```bash
sbt
> ~ testQuick
```