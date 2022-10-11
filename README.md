# dev_HadoopAIO
AIO Hadoop Build

#### Components to Includes:
- Hadoop
- Spark
- Hive
- HBase
- Pig
- Flume
- Tez
- Zeppelin
- ODBC
- JDBC

#### Docker AIO with Hadoop, Spark, H2O
- Build image
  ```
  $docker build -t hadoop_aio:v1 .
  ```

- Launch Command:
  ```
  $docker run -it --rm -p 18080:18080 -p 18989:8989 -p 54321:54321 <image_id> bash 
  ```

#### Sparkling Water Info:
- Documentation
  [https://s3.amazonaws.com/h2o-release/sparkling-water/spark-2.4/3.38.0.1-1-2.4/index.html](https://s3.amazonaws.com/h2o-release/sparkling-water/spark-2.4/3.38.0.1-1-2.4/index.html) <br/>
