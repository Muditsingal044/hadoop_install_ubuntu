# hadoop_install_ubuntu



## Hadoop Installation In Ubuntu

************************************************************************
 
CMD - 

1. sudo apt-get install openjdk-8-jdk

2. sudo apt-get install ssh

3. sudo apt-get install ssh

4. nano .bashrc

(copy and paste in bashrc file)

export PDSH_RCMD_TYPE=ssh  
export HADOOP_HOME="/home/__name__/hadoop"
export PATH=$PATH:$HADOOP_HOME/bin
export PATH=$PATH:$HADOOP_HOME/sbin 
export HADOOP_MAPRED_HOME=${HADOOP_HOME}
export HADOOP_COMMON_HOME=${HADOOP_HOME}
export HADOOP_HDFS_HOME=${HADOOP_HOME}
export YARN_HOME=${HADOOP_HOME}


5. ssh-keygen -t rsa -P ""

6. cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys

7. ssh localhost

8. wget https://dlcdn.apache.org/hadoop/common/hadoop-3.4.0/hadoop-3.4.0.tar.gz

9. tar xzf hadoop-3.4.0.tar.gz

10. hadoop-env        (..open the file in hadoop folder)

export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64/













11. core-site.xml          (..open the file in hadoop folder)

<configuration>
    <property>
        <name>fs.defaultFS</name>
        <value>hdfs://localhost:9000</value>
    </property>
    <property>
        <name>hadoop.tmp.dir</name>
        <value>/home/__name__/tmp</value>
    </property>
</configuration>


12. hdfs-site.xml         (..open the file in hadoop folder)

<configuration>
<property>
        <name>dfs.replication</name>
        <value>1</value>
    </property>
</configuration>


13. mapred-site.xml           (..open the file in hadoop folder)

<configuration>

  <property>
        <name>mapreduce.framework.name</name>
        <value>yarn</value>
    </property>
    <property>
        <name>yarn.app.mapreduce.am.env</name>
        <value>HADOOP_MAPRED_HOME=/home/__name__/hadoop</value>
    </property>
    <property>
        <name>mapreduce.map.env</name>
        <value>HADOOP_MAPRED_HOME=/home/__name__/hadoop</value>
    </property>
    <property>
        <name>mapreduce.reduce.env</name>
        <value>HADOOP_MAPRED_HOME=/home/__name__/hadoop</value>
    </property>
</configuration>








14. yarn-site.xml            (..open the file in hadoop folder)

<configuration>

 <property>
        <name>yarn.nodemanager.aux-services</name>
        <value>mapreduce_shuffle</value>
    </property>
    <property>
        <name>yarn.nodemanager.aux-services.mapreduce.shuffle.class</name>
        <value>org.apache.hadoop.mapred.ShuffleHandler</value>
    </property> 

</configuration>    


CMD - 

15.  cd hadoop      (…. go to hadoop folder )

16. bin/hdfs namenode -format

17. start-all.sh

18. jps


*******************************THANKYOU**********************************
