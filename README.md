# How to use

まずは Franz をダウンロードし、インストール。アカウントを作成して、最初に仮で何かサービスを一つ追加する。

https://meetfranz.com/


Franz のフォルダに移動

````
$ cd ~/Library/Application\ Support/Franz/recipes/
````

ls でフォルダを確認してなければ dev　フォルダを作成し、移動する。

````
$ ls 
gmail	temp
$ mkdir dev
$ cd dev
````

chatbox という名称で Clone

````
$ git clone https://github.com/chatbox-inc/franz-recipe-chatbox chatbox
Cloning into 'chatbox'...
remote: Counting objects: 34, done.
remote: Compressing objects: 100% (16/16), done.
remote: Total 34 (delta 5), reused 20 (delta 4), pack-reused 13
Unpacking objects: 100% (34/34), done.
````

Cmd + Shift + R で　Franz を再起動し Cmd + N でサービスの追加を開くと、開発版が選択可能になるため、chatboxを追加する。

## その他のBacklog を追加する場合

dev ディレクトリ内で chatbox をコピー

````
$ cp -R chatbox hoge
````

package.json を以下３箇所書き換え

````
{
  "id": "{NAME}",
  "name": "{NAME}",
  ....
  "config": {
    "serviceURL": "https://{BACKLOG_SUBDOMAIN}.backlog.jp",
    ....
  }
}
````

アイコンはログイン状態で https://{BACKLOG_SUBDOMAIN}.backlog.jp/SpaceImage.action にアクセスして習得できるので置き換え

SVG の生成は convert が入っていれば

````
$ convert icon.png icon.svg 
````

で行けるはず。

Cmd + Shift + R で　Franz を再起動し Cmd + N でサービスの追加を開くと、作成したチームが追加されているはず。
