# 在本地電腦內找到設定檔

從本地電腦的用戶家目錄內，找到 .aws資料夾，點擊進入後，找到config檔案

打開config檔案，貼入下方config

```
[profile web]
role_arn = arn:aws:iam::129729052534:role/studentRole
# credential_source = EcsContainer
source_profile=default
role_session_name = developer-lbh 
```

將account-id與role的名字，更改為先前建立的role

# 透過role去調度s3資源

先以用戶身分調度，發現失敗
```
aws s3 ls 
```

再以role身份調度
aws s3 ls –-profile web

