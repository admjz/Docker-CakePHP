# Docker-cakephp

## 新規で案件を追加する場合
### ファイルを追加・編集
+ *projectsディレクトリ*配下に追加
+ *docker-compose.yml*のnginxのところでポートを指定
+ *nginxディレクトリ*下にconfファイルを作成

### Dockerに反映

```
docker-compose up -d
```