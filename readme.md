# キャリアシートURL
#### PROD
https://ida-mode.com/entry/r0/

#### Dev1
https://dev.ida-mode.com/entry/r0/

#### Dev2
https://dev2.ida-mode.com/entry/r0/


# Pipelines
ファイルが変更されるとS3へ自動でデプロイされます。  

|  ブランチ  |  S3バケット  |
| ---- | ---- |
|  master  |  ida-public  |
|  dev1  |  dev-ida-public  |
|  dev2  |  dev2-ida-public  |

# 推奨手順
### 前提
htmlファイルはブランチごとに異なる。  
js、css、imgなどその他のファイルはブランチ間で共有する。

### htmlの変更
ブランチごとに編集、コミット、push

### 共有ファイルの変更
dev1(もしくはdev2)で編集、コミット、push  
dev1(もしくはdev2)にデプロイされる  
確認  
masterに切り替える  
チェリーピック  `git cherry-pick {コミット番号}`  
push  
prodにデプロイされる

### 補足
デプロイしたくないファイルはbitbucket-pipelines.ymlのEXTRA_ARGSに記載する。
