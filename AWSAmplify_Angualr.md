
# Windows 10にVisual Studio CodeとGitをインストールする

[Windows 10にVisual Studio CodeとGitをインストールする](https://taccuma.com/install-vscode-and-git-in-win10/)

1. 以下サイトからインストーラをダウンロード
[git for windows](https://gitforwindows.org/)
2. インストール
3. GitHub 初期設定
> git config --global user.name "GitHubに登録しているユーザー名"
> git config --global user.email GitHubに登録しているメールアドレス
> git config --global core.quotepath false #日本語ファイル名がエスケープされないように
`C:\Users\akihi\.gitconfig`に設定される。


# VSCode + GitHub

[GitHubとVSCODEの連携方法](https://qiita.com/yu0313/items/4f95fc0b7e544c42e107)


# GitHub SSH
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
  > HostName github.com
  > IdentityFile ~/.ssh/id_git_rsa #ここに自分の鍵のファイル名
  > User git

4. GitHub に公開鍵を登録する
   'New SSH Key' → `Key` に公開鍵の中身を貼り付け

5. 接続確認
  > ssh -T git@github.com
  > Hi mitapach! You've successfully authenticated, but GitHub does not provide shell access.


# AWS Amplify Console を利用したCI/CD 環境 for Angular

[Github-サインイン](https://github.com/login?return_to=%2Fjoin)


1. プロジェクトフォルダを作成する
   > mkdir amplify-console-angular
   > cd amplify-console-angular

2. angular/cli をローカルインストールする
   > npm i @angular/cli

3. Angular プロジェクトを作成する
   > npx ng new amplify-console-angular --directory=./  
   ※カレントディレクトリに作成する。

4. Githubにpushする
   >git remote add origin https://github.com/mitapach/amplify-console-angular.git
   >git push -u origin master

5. a
6. 





# URL
[超簡単にサイト公開できるAWS Amplify Consoleを使ってAngularのCI/CD環境を作ってみる](https://dev.classmethod.jp/cloud/aws-amplify-console-angular-ci-cd/)


# AWS Amplify Angular 

# AWS
[AWS マネジメントコンソール](https://ap-northeast-1.console.aws.amazon.com/console/home?region=ap-northeast-1#)
[Amazon Cognito](https://ap-northeast-1.console.aws.amazon.com/cognito/home?region=ap-northeast-1#)




# 参考
[AWS Amplify + AngularでサーバーレスSPAの認証をするサンプル](https://qiita.com/daikiojm/items/18f718df07c28965b7b3)


