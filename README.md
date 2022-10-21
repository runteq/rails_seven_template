## プロジェクトのセットアップ手順

### railsサーバーの起動

```
docker-compose build
docker-compose run web bundle install
docker-compose run web yarn install
docker-compose up
```

### CSS, JS用のサーバー起動(ターミナルを複数開いて別タブで入力してください)

```
docker-compose run web bin/dev
```

## 各コマンドについて

### Dockerイメージの構築

```bash
docker-compose build
```

### Dockerコンテナの構築&起動

#### 通常の起動

```bash
docker-compose up
```

#### バックグラウンドで起動
```bash
docker-compose up -d
```

### Dockerコンテナを終了する

```bash
docker-compose down
```

### データベースの作成

```bash
docker-compose run web rails db:create
```

### jsファイル&sassファイルのビルド&変更反映用

```bash
docker-compose run web bin/dev
```

## Dockerを使う上での注意点

### Gemfileを編集したらDockerイメージに変更を反映させる

#### bundle installする

```bash
docker-compose run web bundle install
```

#### GemfileとGemfile.lockを反映する

```bash
docker-compose build --force-rm
```

### デバッグツールを使うときは

#### railsサーバーを立ち上げているコンテナのIDを確認する

```bash
docker container ls
```

#### 該当のコンテナIDをattachする

```bash
docker attach コンテナID
```
