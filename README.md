# Dockerコンテナ上でAngular開発するベース

## 環境構築

1. docker環境に移動

    ```shell
    %cd dir
    ```

1. angular cli環境を作成する

    ```shell
    %docker compose up
    ```

1. angular cli でアプリケーション作成。コンテナ内でngコマンドとインタラクティブなやりとりが発生するとうまくいかないのでデフォルト値を指定。

    ```shell
    %docker compose run --rm -T app ng new tutorial --directory . --defaults --skip-git
    ```

## 開発

* アプリをビルドしてホストする

    ```shell
    %docker compose up
    ```

* パッケージなどを追加でインストールする

    ```shell
    %docker compose run --rm app npm install @types/moment
    ```

* シェルを起動する

    ```shell
    %docker compose run --rm app /bin/bash
    ```

## 補足

* gitのリポジトリは本ベースプロジェクトではなく，angular cliが作った dir/.gitを使う．

## 課題

* 単体テストの実行環境構築手順が未調査
  * headless chromeのインストール手順をDockerFileに追加する必要がある．
    * 参考：<https://github.com/cats-oss/docker-node-headless-chrome>
  * angular.jsonにheadless chromeを使う手順を記載する必要がある．
