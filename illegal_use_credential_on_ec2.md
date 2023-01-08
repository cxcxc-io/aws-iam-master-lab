# 同仁寫出來的不正確腳本

```
#!/bin/bash
export AWS_ACCESS_KEY_ID=YOUR_AWS_ACCESS_KEY_ID
export AWS_SECRET_ACCESS_KEY=YOUR_AWS_SECRET_ACCESS_KEY
aws s3 ls
```

# 將同仁的腳本複製後，貼入EC2內執行

編輯檔案

`vim app.sh`

按 i，進入編輯模式

複製文件頂端的腳本，並用滑鼠右鍵貼上

貼上後，將AWS_ACCESS_KEY_ID與AWS_SECRET_ACCESS_KEY的內容修改為
開發者的Credential

更改完成後，點擊ESC按鍵，輸入:wq 進行存檔

`:wq`

執行檔案

`sh app.sh`

# 透過IAM Console 停權用戶的Credential

# 連回EC2，重新執行檔案

`sh app.sh`

發現檔案無法執行成功, 請同仁重改程式碼


# 移除有用戶憑證的那兩句內容

`vim app.sh`

按 i，進入編輯模式

將游標移至下述兩句話，移除

```
export AWS_ACCESS_KEY_ID=YOUR_AWS_ACCESS_KEY_ID
export AWS_SECRET_ACCESS_KEY=YOUR_AWS_SECRET_ACCESS_KEY
```

更改完成後，點擊ESC按鍵，輸入:wq 進行存檔

`:wq`

執行檔案

`sh app.sh`
