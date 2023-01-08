# 取得用戶的Credentail

切換IAM Console，找到開發部門的User，切換Secure Credential分頁，為其派發一組Credential

打開觀看後，秉鴻老師提出靈魂問句

# 安裝aws cli，並確認是否安裝成功

請大家假裝自己是同仁，用瀏覽器搜尋aws cli，進入官方頁面後，下載安裝

打開命令列，輸入aws --version，確認有安裝成功

`aws --version`

# 註冊與使用credential

輸入aws s3 ls，發現無法瀏覽

`aws s3 ls`

輸入aws configure，進行註冊，輸入先前得到的Credential，並指定區域為東京(ap-northeast-1)

`aws configure`

再次輸入aws configure，確認已有輸入

`aws configure`

輸入aws s3 ls，瀏覽所有Bucket

`aws s3 ls`

# 挖掘出隱藏在本地端的aws credential

打開檔案總管，搜尋家目錄，找到 .aws資料夾，發現config檔案與credentials檔案
. 老師打開credentials檔案。 