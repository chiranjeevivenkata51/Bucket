/*Dynamic partition to nonstrict,enabling the Bucketing,Changing the default size of the partition*/
hive> SET hive.exec.dynamic.partition=true;
hive> SET hive.exec.dynamic.partition.mode=non-strict;
hive> SET hive.enforce.bucketing=true;
hive> SET hive.exec.max.dynamic.partition.pernode=250;
hive> create table cb(na string,ag string,ye string,date string,ca string,med string,cz string,cze string,czm string) partitioned by(co string) clustered by(ye) into 5 buckets row format delimited fields terminated by ',';
hive> insert overwrite table cb partition(co) select na,ag,ye,date,ca,med,cz,cze,czm,co from ol;
