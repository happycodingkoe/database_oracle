#Case 0001 : 
** Note Error :

Error : ORA-01033: ORACLE initialization or shutdown in progress
Oracle DB Version : 12.2.0

** Note Command

sqlplus hr@orclpdb
sqlplus / as sysdba
show con_name
show pdbs
alter pluggable database orclpdb open read write ;
alter session set container = orclpdb ;
show con_name

Full steps are available in github :

Github : https://github.com/happycodingkoe/database_oracle
Blog : https://happycodingkoe.blogspot.com/
IG : @happycodingkoe
FB : https://web.facebook.com/happycoding.koe.3