## 環境構築


### [must]docker-compose.ymlの編集
1. docker-composeで使用したいcontainer名(何でもOK, devなど)
2. 


### [optional]wandbの設定
- wandbを使用する場合は、wandbのアクセスキーを入力する
```
cp env/wandb.env.tmp env/wandb.env
# wandb.envに自分のアクセスキーを入力する
```
- また、wandbのプロジェクト名をdocker-compose.ymlに入力する
```

```

### docker環境の構築 & 起動
```{bash}
git clone git@github.com:{your-new-project-name}
cd {your-new-project-name}/env
docker compose build {your-new-docker-name}
docker compose up {your-new-docker-name} -d 
docker compose exec {your-new-docker-name} /bin/bash
```