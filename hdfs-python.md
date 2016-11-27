# Install hadoop hdfs
http://hadoop.apache.org/docs/stable/hadoop-project-dist/hadoop-common/SingleCluster.html

# Enable webhdfs
https://bighadoop.wordpress.com/2013/06/02/hadoop-rest-api-webhdfs/

Modify etc/hadoop/hdfs-site.xml by adding following property:

    <property>
      <name>dfs.webhdfs.enabled</name>
      <value>true</value>
    </property>

# Start hdfs
Run command to start hdfs:

    sbin/start-dfs.sh

# Install pywebhdfs client
Use pip to install

    pip install --user pywebhdfs

# Examples
Examples can be found at http://pythonhosted.org/pywebhdfs/

    from pywebhdfs.webhdfs import PyWebHdfsClient
    hdfs = PyWebHdfsClient(host='localhost',port='50070', user_name='xmwang')
    hdfs.list_dir('/')
