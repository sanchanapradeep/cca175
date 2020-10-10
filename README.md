# cca175
certificcation cca175


1. Quick start Spark-shell
2. Quick reference




# Start Spark local:
spark-shell

# start spark remotely:

spark-shell --master yarn \
  --spark.ui.port=12654
  
# spark with number of executors and memory
spark-shell --master yarn \
  --spark.ui.port=12654 \
  --num-executors 1 \
  --executor-memory 512M
  
  # spark-shell = spark + spark-dependency + implicit variables sc and sqlcontext
  
  sc  -> spark context is a web interface that is why we give port
  
  # defalut configs:
  
  cd /etc/spark/conf/spark-defaults.conf
  spark-env.sh
  
  to stop spark context
  sc.stop()
  
  # create a new one:
  val conf = new sparkconf().setapp("daily revenue").setmaster("yarn_client")
  val sc= new sparkcontext(conf)
  sc.getconf.getAll
  
# create an RDD
```hadoop comamnd:```
hadoop fs -ls /public/retail_db/orders
```hadoop tail:```hadoop fs -tail <file name> (/public/retail_db/orders/part-0000)
  
 # read a file and create an RDD
 val orders = sc.textFile("/public/retail_db/orders")
 
 #read 1st element
  order.first
 #read first 10 element
  order.take(10)
   above command creates an RDD from hadoop file .
   If u want to create an RDD from file on hard disk
   ```steps:```
   
  
  
