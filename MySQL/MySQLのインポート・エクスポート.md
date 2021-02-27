---
name: "MySQLのインポート・エクスポート"
slug: "izmrxiq"
tags: ["MySQL"]
---

# MySQLのインポート・エクスポート

## インポート

```
mysql -u[DB_USER] -p[DB_PASSWORD] [DB_NAME] < mysql.dump
```


## エクスポート

```
mysqldump -u [DB_USER] -p -h [HOST_NAME] [DB_NAME] > [OUTPUT_FILE_NAME]
```


## エクスポートのオプション

```
--default-character-set=binary
```

