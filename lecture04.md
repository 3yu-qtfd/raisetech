------------------------------------------------------------------------------------------------------------------
# AWS環境構築（VPC、EC2、RDS）
------------------------------------------------------------------------------------------------------------------

### 課題内容
AWS上にVPC、EC2、RDSを構築のうえEC2からRDSへ正常に接続出来ることを確認する。

### 構築した環境
1. VPC<br>
- VPCのウィザードを活用し、プライベートサブネット、パブリックサブネットを作成する。
<img width="965" alt="vpc" src="https://user-images.githubusercontent.com/118968276/233093924-472896c1-5580-4e1c-b4f9-2bccf8e3466d.png">

2. EC2<br>
- Amazon Linuxのインスタンスを起動する。
<img width="981" alt="ec2_01" src="https://user-images.githubusercontent.com/118968276/233093992-ec7e325a-17c1-49ae-b260-f16e952da0de.png">

- セキュリティグループを作成し、外部からEC2への接続を許可する。
<img width="991" alt="ec2_02" src="https://user-images.githubusercontent.com/118968276/233094021-b614b7f0-4c91-4234-b960-52e2cc72f336.png">

3. RDS<br>
- MySQLを選択しRDSを起動する。
<img width="991" alt="rds_01" src="https://user-images.githubusercontent.com/118968276/233094050-91e0da21-70cf-488e-8c6a-89522aa8bc9c.png">


- サブネットグループでプライベートサブネットを2つ割り当て、
セキュリティグループを作成してEC2からRDSへの接続を許可する。<br>

  - ルール1
<img width="994" alt="rds_02" src="https://user-images.githubusercontent.com/118968276/233094097-5761fc40-6434-4423-a5ba-8674c3c58d95.png">

  - ルール2
<img width="994" alt="rds_03" src="https://user-images.githubusercontent.com/118968276/233094128-d18eb1c4-6a24-43ea-97cd-720ce1cfbe59.png">

4. EC2（MySQLクライアント）<br>
Amazon LinuxのインスタンスからMySQLに接続するために必要。
MySQLに必要なリポジトリをダウンロードのうえ、yumコマンドでクライアントをインストールする。


### EC2からRDSへの接続確認
RDSのエンドポイント、MySQL用のポート番号、ユーザ名を指定して接続。<br>
RDS作成時に設定したパスワードを入力して接続できたことを確認。
<img width="737" alt="mysql" src="https://user-images.githubusercontent.com/118968276/233097454-ff0ff08d-8ad9-4f05-a872-87358510f4d6.png">