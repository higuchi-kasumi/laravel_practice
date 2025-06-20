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
#### INSERT INTO todos ('id','content','created_at','updated_at') values ('','','','');

### redirect()->route()は何をしているか
#### 名前付きルートtodo.indexにリダイレクトしている。

## その他

### テーブル構成をマイグレーションファイルで管理するメリット
#### マイグレーションファイルとはデータベースの履歴管理ツール

### マイグレーションファイルのup()、down()は何のコマンドを実行した時に呼び出されるのか
#### up()はphp artisan migrate、down()はphp artisan migrate:rollback

### Seederクラスの役割は何か
#### データベースに初期データを追加するためのクラス

### route関数の引数・返り値・使用するメリット
#### 第一引数が名前付きルート、第二引数がパラメータ、返り値は文字列、URLを変更した場合はルート定義をしている一か所のみの修正で済む

### @extends・@section・@yieldの関係性とbladeを分割するメリット
#### @extendsで継承する親を指定。継承先の子Bladeの@section('content') ~ @endsectionで囲われた部分を、親Bladeの@yield('content')の部分に挿入。引数に同じ文字列を指定することで、@section()と@yield()を紐づけている。メリットは共通箇所の変更は親bladeを変更するだけで済むため保守性が上がる。共通部分は記載する必要がなくなるため開発速度が上がる。

### @csrfは何のための記述か
#### CSRF対策のため。トークンが含まれたinputタグの生成・認証をしてくれる。

### {{ }}とは何の省略系か
#### PHP表示の省略形。<?php echo e($変数); ?>
