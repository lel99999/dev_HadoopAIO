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

#### HDP Notes
- Ambari SSL Configuration
  - [https://docs.cloudera.com/HDPDocuments/Ambari-2.2.1.1/bk_Ambari_Security_Guide/content/_optional_set_up_ssl_for_ambari.html](https://docs.cloudera.com/HDPDocuments/Ambari-2.2.1.1/bk_Ambari_Security_Guide/content/_optional_set_up_ssl_for_ambari.html) <br/>
  - [https://docs.cloudera.com/HDPDocuments/Ambari-2.2.1.1/bk_Ambari_Security_Guide/content/_set_up_truststore_for_ambari_server.html](https://docs.cloudera.com/HDPDocuments/Ambari-2.2.1.1/bk_Ambari_Security_Guide/content/_set_up_truststore_for_ambari_server.html) <br/> 

#### Docker AIO with Hadoop, Spark, H2O
- Build image
  ```
  $docker build -t hadoop_aio:v1 .
  ```

- Launch Command:
  Port Maps: 
  - 18080 : Spark Log Server
  - 18989 : Zeppelin
  - 54321 : H2O

  ```
  ## Ready for H2O
  $docker run -it --rm -p 18080:18080 -p 18989:8989 -p 54321:54321 <image_id> bash 
  root@<image_id>:/workdir$cd /opt/h2o-3.38.0.1
  root@<image_id:/opt/h2o-3.38.0.1$java -jar h2o.jar &
  ## Should now be able to open http://localhost:54321 in browser

  ## Mount Volume Local (/tmp/h2o_datadir) to Container (/mnt/DataDir)
  $docker run -it --rm -p 18080:18080 -p 18989:8989 -p 54321:54321 -v /tmp/h2o_datadir:/mnt/DataDir <image_id> bash
  ```

#### Sparkling Water Info:
- Documentation
  [https://s3.amazonaws.com/h2o-release/sparkling-water/spark-2.4/3.38.0.1-1-2.4/index.html](https://s3.amazonaws.com/h2o-release/sparkling-water/spark-2.4/3.38.0.1-1-2.4/index.html) <br/>
