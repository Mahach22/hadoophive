ARG HIVE_VERSION
FROM docker.io/apache/hive:${HIVE_VERSION}

# Switch to root user to perform actions that require root permissions
USER root

# Remove the conflicting SLF4J binding
RUN rm /opt/tez/lib/slf4j-reload4j-1.7.36.jar

COPY core-site.xml $HADOOP_HOME/etc/hadoop/core-site.xml
COPY hdfs-site.xml $HADOOP_HOME/etc/hadoop/hdfs-site.xml

# Start HiveServer2
CMD /opt/hive/bin/hive --skiphadoopversion --skiphbasecp --service hiveserver2
