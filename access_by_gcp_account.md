# 乙方將他的帳號id交給甲方進行設定 

我猜想現在徐大哥還在位置上，由他來配合我們演出，他是甲方，我演使用GCP的乙方。

先由我用GCP取出 account-id，交付給徐大哥 

徐大哥用管理員身份，切換回aws iam console，建立一個role

輸入我的gcp account-id後，選擇S3 ReadOnly access權限，並把role的arn交付給我

# 乙方在其系統內調度甲方的aws

## 環境準備
我打開gcp 的cloud shell，並安裝awscli

`sudo pip3 install awscli`

## 乙方取得乙方系統的安全憑證
先透過gcp的命令列，取得安全憑證

`gcloud auth print-identity-token --impersonate-service-account=“cxcxc-web-demo@cxcxc-demo-2022-11-26-cxcxc.iam.gserviceaccount.com” --include-email > aws_temp_cred`

## 將安全憑證設定在.aws/config內

將該安全憑證輸入至.aws/config內

```
mkdir .aws
vim .aws/config
```

貼入設定檔，並修改

```
[profile access-by-gcp]
role_arn = arn:aws:iam::129729052534:role/from_gcp_sa
web_identity_token_file=aws_temp_cred
role_session_name = developer_lbh 
```

先輸入aws s3 ls，發現無法使用

`aws s3 ls`

輸入 aws s3 ls --profile web，發現可用

`aws s3 ls --profile web`