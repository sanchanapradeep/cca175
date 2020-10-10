# cca175
certificcation cca175




# Start Spark local:
spark-shell

# Start spark remotely:

spark-shell --master yarn \
  --spark.ui.port=12654
  
# Spark with number of executors and memory
spark-shell --master yarn \
  --spark.ui.port=12654 \
  --num-executors 1 \
  --executor-memory 512M
  
  # spark-shell = spark + spark-dependency + implicit variables sc and sqlcontext
  
  sc  -> spark context is a web interface that is why we give port
  
  # Defalut configs:
  
  cd /etc/spark/conf/spark-defaults.conf
  spark-env.sh
  
  to stop spark context
  sc.stop()
  
  # Create a new one:
  val conf = new sparkconf().setapp("daily revenue").setmaster("yarn_client")
  val sc= new sparkcontext(conf)
  sc.getconf.getAll
  
# Create an RDD
```hadoop comamnd:```
hadoop fs -ls /public/retail_db/orders
```hadoop tail:```hadoop fs -tail <file name> (/public/retail_db/orders/part-0000)
  
 # Read a file and create an RDD
 val orders = sc.textFile("/public/retail_db/orders")
 
 # Read 1st element
  order.first
 # Read first 10 element
  order.take(10)
   above command creates an RDD from hadoop file .
 # If u want to create an RDD from file local file system
   ```steps:```
   1. read the file  and convert to list(e.g, val productRaw = scala.io.Source.fromFile("/data/retail_db/products/part-0000").getLines.toList)
   2. apply parallize (eg: val productsRdd =sc.parallize(productRaw)
   
  # 1 to 100 numbers to list
  val l = (1 to 100).toList
  # convert to rdd
  val l_rdd = sc.parallize(l)
  
  # Spark APIs are catagirised under based on lazy evaluation.
  1. transformations 
  2. actions (only performed under action is performed, lazyly executed) performed under DAG (directed acyclic graph)
 order.debug
 
 dag visuvalization can be seen in UI
 click on jobs-> click on job u wnat to see the DAG -> click on DAG visuvalization
  refer the image 
  


  
  
  
  
  
  
  
