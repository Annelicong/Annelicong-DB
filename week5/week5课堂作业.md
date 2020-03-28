# SQL实践-课堂作业

![作业要求](https://upload-images.jianshu.io/upload_images/22283304-5b05384e4836fb41.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

1. 简单查询
``` 
mysql>  use `week5-db`;
Database changed
mysql> select * from student;
+-----+-------+------+-----------+-------+
| sno | sname | ssex | sbirthday | class |
+-----+-------+------+-----------+-------+
| 101 | 李军  | 男   |      1976 | 95033 |
| 103 | 陆君  | 男   |      1974 | 95031 |
| 104 | 尚文  | 男   |      1978 | 95033 |
| 105 | 框明  | 男   |      1975 | 95031 |
| 107 | 王丽  | 女   |      1976 | 95033 |
| 108 | 曾华  | 男   |      1977 | 95033 |
| 109 | 王芳  | 女   |      1977 | 95031 |
+-----+-------+------+-----------+-------+
7 rows in set (0.00 sec)
```
2. 查询结果返回元组的排序
```
mysql> select * from student order by sno asc;
+-----+-------+------+-----------+-------+
| sno | sname | ssex | sbirthday | class |
+-----+-------+------+-----------+-------+
| 101 | 李军  | 男   |      1976 | 95033 |
| 103 | 陆君  | 男   |      1974 | 95031 |
| 104 | 尚文  | 男   |      1978 | 95033 |
| 105 | 框明  | 男   |      1975 | 95031 |
| 107 | 王丽  | 女   |      1976 | 95033 |
| 108 | 曾华  | 男   |      1977 | 95033 |
| 109 | 王芳  | 女   |      1977 | 95031 |
+-----+-------+------+-----------+-------+
7 rows in set (0.00 sec)
```
3. 涉及字符串的查询：模糊查询、全文检索
```
mysql> select sname from student where sname regexp '李+';
+-------+
| sname |
+-------+
| 李军  |
+-------+
1 row in set (0.17 sec)
```
``` 
mysql> alter table student add fulltext index idx_full_keyword(sname);
Query OK, 0 rows affected, 1 warning (11.19 sec)
Records: 0  Duplicates: 0  Warnings: 1
```