---
name: "MySQLの基本的なコマンド"
slug: "ochdrhh"
tags: ["MySQL"]
---

# MySQLの基本的なコマンド

## 基本

```sql
INSERT INTO 表名(列名1,列名2) VALUES(値1,値2)
```

```sql
UPDATE 表名 SET 列名1=値1, 列名2=値2 WHERE 列名1=値1
```

```sql
DELETE FROM 表名 WHERE 列名1=値1
```

```sql
DROP DATABASE IF EXISTS DB名
```


## ALTER TABLE

```sql
ALTER TABLE 表名 ADD 列名 データ型;
```

### オートインクリメントのリセット

```sql
ALTER TABLE 表名 auto_increment = 1;
```



