# Laravel Lesson レビュー②

## Todo編集機能

### @method('PUT')を記述した行に何が出力されているか
```HTML
<input type="hidden" name="method" value="PUT">
```
#### POSTで送るが、PUTとして処理するようにしている

### findメソッドの引数に指定しているIDは何のIDか
#### ユーザーが選択したID

### findメソッドで実行しているSQLは何か
```PHP
select * from `todos` where `id` = $id limit 1;
```

### findメソッドで取得できる値は何か
#### Todoオブジェクト型

### saveメソッドは何を基準にINSERTとUPDATEを切り替えているのか
#### 主キーがNULLならINSERT、主キーに値がある場合はUPDATE

## Todo論理削除

### traitとclassの違いとは
#### classはオブジェクトの設計図で、インスタンス化してオブジェクトを作成できる。traitはclassに機能を追加するためのもので、インスタンス化はできない。

### traitを使用するメリットとは
#### 複数のクラスで同じ処理をしたい場合にuse trait名とクラスに記載するだけでできるから開発の効率があがる。

## その他

### TodoControllerクラスのコンストラクタはどのタイミングで実行されるか
#### ルート定義でTodoControllerクラスの処理が呼ばれたタイミング

### RequestクラスからFormRequestクラスに変更した理由
#### バリデーションルールを作成したかったため、バリデーションを行えるFormRequestクラスに変更した。

### $errorsのhasメソッドの引数・返り値は何か
#### 引数は入力欄のname属性、返り値はbool型

### $errorsのfirstメソッドの引数・返り値は何か
#### 引数は入力欄のname属性、返り値は文字列

### フレームワークとは何か
#### アプリケーション開発を効率的に行うための枠組みや構造を提供するソフトウェアのこと

### MVCはどういったアーキテクチャか
#### アプリケーションをModel、View、Controllerの3つの役割に分割するソフトウェア設計パターンのこと。

### ORMとは何か、またLaravelが使用しているORMは何か
#### ORMとはClassとデータベースのテーブルを関連付けることでSQLを直接操作することなく、データベースとマッピングされたClassのメソッドを用いることでDBを操作できる仕組みのこと

### composer.json, composer.lockとは何か
#### composer.jsonはインストールしたいパッケージ一覧を表示するファイルで、omposer.lockは実際にインストールしたパッケージのバージョンなどの情報が自動的に記録されるファイル

### composerでインストールしたパッケージ（ライブラリ）はどのディレクトリに格納されるのか
#### venderディレクトリ
