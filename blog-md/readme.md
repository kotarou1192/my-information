# BLOG.md

QiitaやZennなどのサービスをよく目にするたびに、日記などの些細なことでもmarkdownで書くことできればいいなと思っていました。  
このサイトはその点を取り入れ、markdownにて記事などを好きなように書くことができます。  

利用はブラウザ(chrome)推奨です。

<https://blog-md.net>

## 使い方

### ログインをしない場合

ユーザーや記事の閲覧・検索のみができます

トップページには最新の記事が表示されています。  
表示されている記事をクリックすると、記事ページに飛びます。

上の検索欄に文字を入れエンターを押すと、ユーザーや記事を検索して閲覧できます。  
キーワードは空白で区切ってください。

### 登録する場合

登録をするとフォローや記事投稿・編集・削除をすることができます。

![img1](./buttons.png)

こちらのsign upからメールを送信し、届いたメールから登録リンクへ飛んだあとに必要情報を記入して登録ください。  

すでにアカウントを所持している場合はsign inからログインをお願いします。

### 試用

利用テストのため、ゲスト用アカウントがあります。
email: guest@blog-md.net
password: guest-password

### 使用した技術

#### バックエンド

- ruby
  - ruby on rails
  - capistrano
- redis
- nginx
- postgreSQL
- Google ReCAPTCHA v3

#### フロントエンド

- HTML
- CSS
- TypeScript
  - React.js
    - react-dom-router
  - Webpack
  - material-ui

#### インフラその他

- Let's Encrypt
  - CertBot
- CircleCI
- Amazon
  - Lightsail
    - ディストリビューション(CDN)
    - データベース・サーバ(postgresql)
    - Bucket
    - Instance(ubuntu)
  - AWS Route53


## 開発に際して

GitHubのイシューに欲しい機能をメモし、はじめにWebAPIから実装し、それをブラウザから扱うことができるようにしていきました。  
開発の流れは  
> issueに応じたブランチを切る -> 実装をする -> CIでテストを通してPullRequest -> merge  

上記となっています。  
コミットにもプリフィクスをつけ、何をしたかをわかりやすくするよう心がけていました。

バックエンドに関しては、テストを必ず書き、CircleCI上で通った場合にのみデプロイするようにしていました。  
それにより、リファクタリングにより機能が壊れていないか・仕様通りに動いているか　などのチェックを行うことができました。

画像に関してはRailsにアップロードされた画像をS3二ノ瀬、それをCDNを利用して配信して、サーバーの負荷を減らすように心がけました。  

## リポジトリ

[frontend](https://github.com/kotarou1192/blog_client)  
[backend](https://github.com/kotarou1192/blog_api)
