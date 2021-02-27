---
name: "OpenSSH"
slug: "kxlzlgs"
---

# OpenSSH
## 接続

```
ssh username@example.com
```


### 接続のオプション

| オプション | 説明 |
| --- | --- |
| -p | ポート番号 |
| -i ~/.ssh/id_rsa | 秘密鍵を指定 |
| -F ~/.ssh/config | 設定ファイルを指定 |
| -vvv | デバッグログ出力 |

## ~/.ssh/config

```
Host dev
    HostName        192.168.0.1
    Port            22
    User            admin
    IdentityFile    ~/.ssh/id_rsa
    IdentitiesOnly  yes
```


## パーミッション


| ファイル | パーミッション |
| --- | --- |
| ~ | 700, 711, 755 |
| ~/.ssh | 700 |
| ~/.ssh/authorized_keys | 600 |
| ~/.ssh/id_rsa | 600 |

***~ は Owner 以外に書き込み権限が無いように。***


## ssh-keygen

```
ssh-keygen -t rsa -b 4096
```

