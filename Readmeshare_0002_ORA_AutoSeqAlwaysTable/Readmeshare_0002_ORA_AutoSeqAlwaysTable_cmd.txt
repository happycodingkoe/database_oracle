#Note 0002 : Create table with Auto sequence as always  in Oracle 12c

Github : https://github.com/happycodingkoe/database_oracle
Blog : https://happycodingkoe.blogspot.com/
IG : @happycodingkoe
FB : https://web.facebook.com/happycoding.koe.3

** Note :
Oracle DB Version : 12.2.0

**Note Command
DROP TABLE demo_auto_seq_always;

CREATE TABLE demo_auto_seq_always (
    id NUMBER GENERATED ALWAYS AS IDENTITY START WITH 100 INCREMENT BY 1,
    object_name VARCHAR2(255) NOT NULL
);

INSERT INTO demo_auto_seq_always (object_name) select object_name FROM user_objects;
COMMIT;

SELECT * FROM demo_auto_seq_always WHERE ROWNUM < 10;

SELECT table_name, 
       column_name,
       generation_type,
       identity_options
FROM   all_tab_identity_cols
WHERE  owner = 'HR' and table_name='DEMO_AUTO_SEQ_ALWAYS'
ORDER BY 1, 2;
