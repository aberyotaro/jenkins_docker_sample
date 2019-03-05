# Docker + jenkins

## 手順

### 1. コンテナ起動

```
$ docker-compose up
```

### 2. localhost:8080へアクセス
ブラウザでJenkinsのセットアップを済ます

### 3. rsa鍵生成し、docker-compose.ymlへコピー
```
$ docker exec -ti master ssh-keygen -t rsa -C ""
$ pbcopy < jenkins/.ssh/id_rsa.pub
$ vim docker-compose.yml
# JENKINS_SLAVE_SSH_PUBKEYへコピペ
```

### 4. コンテナを起動し直す
```
$ docker-compose down
$ docker-compose up
```

### 5. localhost:8080へアクセス
Jenkinsの管理 > ノードの管理 > 新規ノード作成
