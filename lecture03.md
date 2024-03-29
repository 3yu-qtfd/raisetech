------------------------------------------------------------------------------------------------------------------
# Webアプリケーションの基礎とRuby on Rails
------------------------------------------------------------------------------------------------------------------

## ◆課題の回答
### サンプルアプリケーションのAPサーバー
- APサーバーの名称：Puma、バージョン：5.6.5  
※rails起動時にPumaのバージョンを確認。

- APサーバー（Puma）を終了させると？  
コンソール上では「exited with code 1」と表示されrailsアプリケーションが終了する。  
ブラウザ上では「No application seems to be here」というエラー画面が表示される。

- APサーバー（Puma）を再起動すると？  
railsアプリケーションが立ち上がり、停止前とは別のpidで実行される。

### サンプルアプリケーションのDBサーバー
- DBサーバーの名称：MySQL、バージョン：8.0.32  
※コンソール上からMySQLへログイン時にバージョンを確認。

- DBサーバー（MySQL）を終了させると？  
コンソール、ブラウザ上で「Can't connect to local MySQL server～」というエラー画面が表示される。

### Railsの構成管理ツール
- Railsの構成管理ツール：Bundler  
- `bundle install`コマンドで必要なライブラリを取得できる。

------------------------------------------------------------------------------------------------------------------

## ◆学んだこと
### クライアントとサーバー
- Webアプリケーションの場合、クライアント：ブラウザ、サーバー：APサーバーとなる。  
 （厳密にはWebサーバーがブラウザとAPサーバーの間の橋渡しを行う）
- この時に用いられるのがHTTPリクエスト（GET,POSTなどで要求）とHTTPレスポンス（完了コード200,504などを返す）。

### APサーバーとDBサーバー
- いずれもミドルウェアで、OSとアプリケーションの中間的な処理を担う。
- APサーバーはアプリケーションプログラムを実行する役割。内部的にWebサーバーを持つこともある。
- DBサーバーはDBにデータを格納し、プログラム実行時にデータをAPサーバーに渡す役割。

### インフラエンジニアとしての役割
- インフラエンジニアがアプリケーション起動の自動化を行うこともある。  
そのため、Webアプリケーションがどのように動くのか、基礎的なことは知っておく必要がある。

### Railsとは
- RailsはRuby言語を利用する際に使われるフレームワーク。ファイルの集まりなので、構成管理ツールが必要。

### 外部ライブラリと構成管理ツール
- 外部ライブラリとは、便利機能をまとめたパッケージのイメージ。（＝アプリの中には無い）
- アプリ開発では数十個～数百個単位で外部ライブラリを使うので、構成管理ツールを活用する。
- 構成管理ツールで、それぞれのアプリケーションに必要な外部ライブラリを定義しておく。  
外部ライブラリをまとめて管理しているリモートリポジトリから、必要なライブラリをダウンロードしてくれる。

### Gem,Bundlerとは
- Rubyのリモートリポジトリ：RubyGems.org（＝外部ライブラリであるGemをまとめて管理）
- RailsもGemの1つであるためダウンロードも可能だが、前提としてGemを動かすためのGem等がたくさん必要になる。
そこで、構成管理ツールBundlerを使う。
- Javaなど他の言語でも、Bundlerと同じような構成管理ツールがある。

------------------------------------------------------------------------------------------------------------------

