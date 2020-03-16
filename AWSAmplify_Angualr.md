# AWS Amplify Console を利用したCI/CD 環境 for Angular


## Windows 10にVisual Studio CodeとGitをインストールする

[Windows 10にVisual Studio CodeとGitをインストールする](https://taccuma.com/install-vscode-and-git-in-win10/)

1. 以下サイトからインストーラをダウンロード
[git for windows](https://gitforwindows.org/)
2. インストール
3. GitHub 初期設定
> git config --global user.name "GitHubに登録しているユーザー名"
> git config --global user.email GitHubに登録しているメールアドレス
> git config --global core.quotepath false #日本語ファイル名がエスケープされないように
`C:\Users\akihi\.gitconfig`に設定される。

> [core]
> 	editor = \"C:\\Users\\akihi\\AppData\\Local\\Programs\\Microsoft VS Code\\Code.exe\" --wait
> 	quotepath = false
> [user]
> 	name = mitapach
> 	email = akihiko.mita@koa.muratec.co.jp
> [push]
> 	default = simple
> [http "https://github.com/"]
> 	proxy = http://172.28.2.113:8080
> [http]
> 	proxy = http://172.28.2.113:8080
> [https]
> 	proxy = http://172.28.2.113:8080


## GitHub SSH 設定

[GitHubとVSCODEの連携方法](https://qiita.com/yu0313/items/4f95fc0b7e544c42e107)

1. 鍵（id_git_rsa）を作成する。
> ssh-keygen -t rsa
> Generating public/private rsa key pair.
Enter file in which to save the key (/Users/(username)/.ssh/id_rsa):id_git_rsa
> Enter passphrase (empty for no passphrase):
> Enter same passphrase again:

* 秘密鍵： .\id_git_rsa
* 公開鍵： .\id_git_rsa.pub

2. 作成した鍵を以下に移動
   `C:\Users\akihi\.ssh`

3. id_git_rsa を利用可能にする
   `C:\Users\akihi\.ssh`に`configファイル`を追加

> Host github github.com
>   HostName github.com
>   IdentityFile ~/.ssh/id_git_rsa #ここに自分の鍵のファイル名
>   User git
> Host ssh.github.com
>   HostName ssh.github.com
>   IdentityFile ~/.ssh/id_git_rsa #ここに自分の鍵のファイル名
>   User git


4. GitHub に公開鍵を登録する
   [Github-サインイン](https://github.com/login?return_to=%2Fjoin)
   'New SSH Key' → `Key` に公開鍵の中身を貼り付け

5. 接続確認
  > ssh -T git@github.com
  > Hi mitapach! You've successfully authenticated, but GitHub does not provide shell access.


## Angular プロジェクトを作成する

1. プロジェクトフォルダを作成する
   > mkdir amplify-console-angular
   > cd amplify-console-angular

2. angular/cli をローカルインストールする
   > npm i @angular/cli

3. Angular プロジェクトを作成する
   > npx ng new amplify-console-angular --directory=./  
   ※カレントディレクトリに作成する。

4. ローカルリポジトリにコミット
   >git add .
   >git commit -m "first commit"

5. Githubにpushする
   >git remote add origin git@github.com:mitapach/amplify-console-angular.git
   >git push -u origin master

## AWS Amplify console を使ってサイトを公開する
[AWS Amplify console を使ってサイトを公開する](https://dev.classmethod.jp/cloud/aws-amplify-console-angular-ci-cd/)

1. Amplify console から登録する。
   [AWS Amplify Console](https://ap-northeast-1.console.aws.amazon.com/amplify/home?region=ap-northeast-1#/home)
   
   From your existing code → GitHub

2. 





# URL
[超簡単にサイト公開できるAWS Amplify Consoleを使ってAngularのCI/CD環境を作ってみる](https://dev.classmethod.jp/cloud/aws-amplify-console-angular-ci-cd/)


# AWS Amplify Angular 

# AWS
[AWS マネジメントコンソール](https://ap-northeast-1.console.aws.amazon.com/console/home?region=ap-northeast-1#)
[Amazon Cognito](https://ap-northeast-1.console.aws.amazon.com/cognito/home?region=ap-northeast-1#)




# 参考
[AWS Amplify + AngularでサーバーレスSPAの認証をするサンプル](https://qiita.com/daikiojm/items/18f718df07c28965b7b3)


