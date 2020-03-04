# 自分用 bcdice-api デプロイ用
[「エクリプス・フェイズ」ダイスボット](https://bitbucket.org/Nanasu/dodontohuyong-eclipe-phase-daisubotsuto)
を追加したのでライセンスは「[クリエイティブ・コモンズ 表示 - 非営利 - 継承 3.0 非移植](https://creativecommons.org/licenses/by-nc-sa/3.0/deed.ja)」。

# BCDice-API

BCDiceを提供するWebAPIサーバー

[![Build Status](https://travis-ci.org/ysakasin/bcdice-api.svg?branch=master)](https://travis-ci.org/ysakasin/bcdice-api)

## Demo

https://bcdice.herokuapp.com

## What is BCDice

BCDiceは日本のTRPGセッションツールにおいて、デファクトスタンダードとも言えるダイスロールエンジンです。
初めは、Faceless氏によってPerlを用いて作成されました。後に、たいたい竹流氏によってRubyへの移植され、現在までメンテナンスされています。

BCDiceは[どどんとふ](http://www.dodontof.com)をはじめとして、[TRPGオンラインセッションSNS](https://trpgsession.click)や[Onset!](https://github.com/kiridaruma/Onset)においてダイスロールエンジンとして使われています。

## Setup

```
$ git clone https://github.com/ysakasin/bcdice-api.git
$ cd bcdice-api
$ git checkout `git describe --abbrev=0` #直近のリリースに移動
$ git submodule init
$ git submodule update
$ bundle install
```

## Run

### Development

```
$ bundle exec rackup
```

### Production

```
$ APP_ENV=production bundle exec rackup -E deployment
```

実際に運用する場合には、[Puma](https://puma.io/)の利用をお勧めします。
- [Running sinatra classic with puma](https://github.com/puma/puma/wiki/Running-sinatra-classic-with-puma)（設定済み）
- [Configuration](https://github.com/puma/puma#configuration)
- [設定例](https://devcenter.heroku.com/articles/deploying-rails-applications-with-the-puma-web-server#config)

## API

Method                           | Description
-------------------------------- | -----
[/v1/version](/docs/api.md#version)   | BCDiceとAPIサーバーのバージョン
[/v1/systems](/docs/api.md#systems)   | ダイスボットのシステムID一覧
[/v1/names](/docs/api.md#names)       | ダイスボットのシステムIDとシステム名前の一覧
[/v1/systeminfo](/docs/api.md#systeminfo)   | ダイスボットのシステム情報取得
[/v1/diceroll](/docs/api.md#diceroll) | ダイスボットのコマンドを実行

## Documents

- [無料で独自ダイスボット入りのBCDice-APIサーバーを立てる](docs/heroku.md) (中級者向け)

## Cases

- [discord-bcdicebot](https://shunshun94.github.io/discord-bcdicebot/)
- [Line botでダイスを振る - Qiita](http://qiita.com/violet2525/items/85607f2cc466a76cca07)
- [HTTPS版BCDice-API | 大ちゃんのいろいろ雑記](https://www.taruki.com/wp/?p=6610) : どどんとふ公式鯖による公開サーバー
- [オンラインセッションツール – Hotch Potch .](https://aimsot.net/tool-info/) : えいむ氏による公開サーバー

## Donate

- [Amazonほしい物リスト](http://amzn.asia/gK5kW6A)
- [Amazonギフト券](https://www.amazon.co.jp/dp/B004N3APGO/) 宛先: ysakasin@gmail.com

## The Auther

酒田　シンジ (@ysakasin)
