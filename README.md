# Hadoop-3.2.2-Installation-Windows

- Download and Install hadoop-3.2.2 from the [Official Hadoop Site](https://hadoop.apache.org/releases.html).
- Create a data folder inside of which create two folders namely, 'datanode' and 'namenode'.
- Edit the following xml files by taking the uploaded files as a reference. You can find them in the 'etc' folder:
  - core-site.xml
    - Here there are two alternatives to try. In case the current file does not work, you can uncomment the code below and try.
  - hdfs-site.xml
    - Here you can even try changing the value attribute from this ```<value>file:///D:/hadoop/data/namenode</value>``` to ```<value>D:\hadoop\data\namenode</value>``` or ```<value>/hadoop/data/namenode</value>``` and see which one works best for you.
  - mapred-site.xml
    - The working file has been uploaded. No alternatives found. 
  - yarn-site.xml
    - The working file has been uploaded. No alternatives found.
- Edit the line ```set JAVA_HOME=%JAVA_HOME%``` by replacing JAVA_HOME with the path to your Java SDK.
    - For example: ```set JAVA_HOME=C:\Progra~2\Java\jdk```
- Set user environment variables for ```HADOOP_HOME``` and ```JAVA_HOME``` and define the same in the system path environment variables too.
- Once all of this is done, opening the command prompt in the 'sbin' folder of hadoop with admin access and run ```hdfs namenode -format```.
- Start the daemons by running the command ```start-dfs && start-yarn```.
- In order to check if all the required processes are up and running, run ```jps```. The output should be somewhat similar to this:
  ~~~ 
  D:\hadoop\sbin>jps
  13216 Jps
  4608 DataNode
  11336 ResourceManager
  23032 NameNode
  1228 NodeManager 
  ~~~
  
You can check these two links to see if a cluster if running:
- ``` http://localhost:8088/cluster ```
- ``` http://localhost:9870/ ```

### Note:
I have only uploaded the folders that required some changes after downloading and installing hadoop from the official site.
There maybe variations in some of the xml files that may work out for you.
If they do then great but if they don't, you can try and take help from these files that I have uploaded.
Hopefully they work for you too!
