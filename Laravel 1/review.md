# Laravel Lesson レビュー①

## Todo一覧機能

### Todoモデルのallメソッドで実行しているSQLは何か
#### SELECT * FROM todos;

### Todoモデルのallメソッドの返り値は何か
#### Collectionオブジェクト

### 配列の代わりにCollectionクラスを使用するメリットは
#### 見た目がシンプルになって、可読性が上がる。モデルメソッドもそのまま使える。

### view関数の第1・第2引数の指定と何をしているか
#### Controllerからbladeファイルへ値を渡す関数で、第１関数は値を渡したいファイル名、第２引数は渡したいデータを指定している

### index.blade.phpの$todos・$todoに代入されているものは何か
#### $todosはTodoControllerのindexメソッドから渡された値が代入されていて、$todoには$todosの各要素が代入されている。

## Todo作成機能

### Requestクラスのallメソッドは何をしているか
#### フォームから送信された値を一括で配列として取得

### fillメソッドは何をしているか
#### Todoインスタンスの各プロパティに$inputsを一括で代入

### $fillableは何のために設定しているか
#### 意図しないカラムを更新させないため。

### saveメソッドで実行しているSQLは何か
#### INSERT INTO todos ('id','content','created_at','updated_at') values (,,,);

### redirect()->route()は何をしているか
#### 名前付きルートtodo.indexにリダイレクトしている。

## その他

### テーブル構成をマイグレーションファイルで管理するメリット
#### 

### マイグレーションファイルのup()、down()は何のコマンドを実行した時に呼び出されるのか

### Seederクラスの役割は何か

### route関数の引数・返り値・使用するメリット

### @extends・@section・@yieldの関係性とbladeを分割するメリット

### @csrfは何のための記述か

### {{ }}とは何の省略系か
