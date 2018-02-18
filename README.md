
<!-- @import "[TOC]" {cmd="toc" depthFrom=1 depthTo=6 orderedList=false} -->
<!-- code_chunk_output -->

* [概要](#概要)
* [環境設定の手順](#環境設定の手順)
	* [1. ローカル環境の用意](#1-ローカル環境の用意)
	* [2. SSH keyの登録](#2-ssh-keyの登録)
	* [3. ソースコードをCLONEする](#3-ソースコードをcloneする)

<!-- /code_chunk_output -->

## 概要  
サブプロジェクト名'Core'、各種BLなどをサーバーサイドを開発します。

## 環境設定の手順  

### 1. ローカル環境の用意
開発者ごとにフォルダの振り分け方とかは違うんですが、環境問題の解決がしやすくなるため一致して頂けます。下記の様に、フォルダを作成してください。

```
C:\Dev_ohhstargram
├── application
|   ├── ohhstargram-core
|   ├── ohhstargram-user
|   ├── ohhstargram-aws
|   ├── ohhstargram-{sub_module_name}
|   └── ...
├── IDE
|   ├── eclipse
├── server
|   ├── tomcat
├── tool
|   ├── maven
|   └── ...
```  
- `application` : プロジェクトのソースコードの収納。後で説明しますが、リもーとリポジトリから`CLONE`します。
- `IDE` : 開発ツールの収納。 `Eclipse(ver.最新)`
- `server` : ロカールサーバーの収納。`Apache Tomcat(ver.8.5)`
- `tool` : 他のツール収納。`maven(ver.3.5.2)`

### 2. SSH keyの登録  
2.1. `Git Bash`を開く : マウスの右クリック⇒`Git Bash Here`クリック  
2.2 下記のコマンドを打つ : SSH keyの作成
```shell
ssh-keygen -t rsa -C "your.email@example.com" -b 4096
```  
上記のコマンドを打ったら`C:\Users\Sangmok Oh\.ssh`の下に`key pair`が作られます。
```
C:\Users\Sangmok Oh\.ssh
├── id_rsa
├── id_rsa.pub
```
※ `id_rsa`は`PRIVATE KEY`なので、絶対に忘れないようにしてください。  
忘れたら、リモートリポジトリからCLONEが出来なくなるため、管理者(@SangmokDavidOh)にお問い合わせしてください。  

2.3 Public keyを開く  
上記の2.1で作った**id_rsa.pub**をさくらエディターで開いて、リモートリポジトリの管理者に送ってください。

### 3. ソースコードをCLONEする
3.1 `Git Bash`を開く
3.2 下記のコマンドを打つ
```bash
cd C:\Dev_ohhstargram\application
git clone git@github.com:SangmokDavidOh/ohhstargram-core.git
```
