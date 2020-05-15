
This explains how to impersonate in Spark Thrift Server (STS) using beeline
MapR 6.1



- With user mapr
```
[mapr@psnode92 ~]$ /opt/mapr/spark/spark-2.4.0/bin/beeline
Warning: Unable to determine $DRILL_HOME
Beeline version 1.2.0-mapr-spark-MEP-6.0.0-1904 by Apache Hive
beeline> !connect jdbc:hive2://psnode90:10000
Connecting to jdbc:hive2://psnode90:10000
Enter username for jdbc:hive2://psnode90:10000: mapr
Enter password for jdbc:hive2://psnode90:10000: ****
Connected to: Apache Hive (version 2.3.3-mapr-1904)
Driver: Hive JDBC (version 1.2.0-mapr-spark-MEP-6.0.0-1904)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://psnode90:10000> insert into a values (40, 'a');
WARNING: Hive-on-MR is deprecated in Hive 2 and may not be available in the future versions. Consider using a different execution engine (i.e. spark, tez) or using Hive 1.X releases.
No rows affected (33.094 seconds)
0: jdbc:hive2://psnode90:10000> [mapr@psnode92 ~]$ exit

mbp-e862:~ mpereira$ ssh randy@10.20.30.92
randy@10.20.30.92's password: 
Last login: Fri May 15 11:24:45 2020
[randy@psnode92 ~]$ /opt/mapr/spark/spark-2.4.0/bin/beeline
Warning: Unable to determine $DRILL_HOME
Beeline version 1.2.0-mapr-spark-MEP-6.0.0-1904 by Apache Hive
beeline> !connect jdbc:hive2://psnode90:10000
Connecting to jdbc:hive2://psnode90:10000
Enter username for jdbc:hive2://psnode90:10000: randy
Enter password for jdbc:hive2://psnode90:10000: *****
Connected to: Apache Hive (version 2.3.3-mapr-1904)
Driver: Hive JDBC (version 1.2.0-mapr-spark-MEP-6.0.0-1904)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://psnode90:10000> insert into a values (41, 'a');
WARNING: Hive-on-MR is deprecated in Hive 2 and may not be available in the future versions. Consider using a different execution engine (i.e. spark, tez) or using Hive 1.X releases.
No rows affected (36.711 seconds)
0: jdbc:hive2://psnode90:10000> [randy@psnode92 ~]$ 
```

