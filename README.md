# wercker-appengine-deploy
werckerでGoogle App Engine(GAE)へgo言語をdeployする。  
Google Cloud Platform(GCP)のCloud SDKが入ったコンテナを使用している。  


## フォルダ構成
```
  wercker.yml
    gae
      app.yaml
```


## environment variables
**SERVICE_ACCOUNT** サービスアカウント  
**SERVICE_ACCOUNT_JSON** サービスアカウント情報(jsonをbase64で)  
**PROJECT_ID** プロジェクトID  


## build
goのビルド環境作成  
golint  
go get  
go build  
go test  


## deploy
サービスアカウントでの認証  
oauth2_access_tokenの取得  
appcfg.py update  


## 備考
gcloud app deployしたかったがうまくいかなかったのでappcfg.py updateでのdeployとなっている  
