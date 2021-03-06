###################################
1.6.3 から 1.7.0 へのアップグレード
###################################

アップグレードの前にはindex.phpを静的ページと置き換えてサイトを停止し
てください。



ステップ 1: CodeIgniter ファイルの更新
======================================

"system"フォルダ内の以下のディレクトリに入っているファイル新しいバージ
ョンのもので置き換えます:


-  system/codeigniter
-  system/database
-  system/helpers
-  system/language
-  system/libraries


.. note:: このディレクトリの中のファイルを更新した場合は、必ず最初にコピーを残しておきます。



Step 2: Session テーブルのアップデート
======================================

アプリケーション内で Sessionクラス を利用していて、なおかつセッション
データをデータベースで管理している場合、セッションテーブルに user_data
という新しいカラムを追加します。 MySQL
の場合だと、このカラムは以下のようになります:


::

	user_data text NOT NULL


このカラムを追加するには、以下のようなクエリを発行します:


::

	ALTER TABLE `ci_sessions` ADD `user_data` text NOT NULL


:doc:`Sessionクラス <../libraries/sessions>` のページに、新しい
Session 機能についてのより詳しい情報が紹介されています。



Step 3: バリデーション構文のアップデート
========================================

これは オプション ですが、現在
Validationクラスを利用されている方は作業される事をおすすめします。CI
1.7 では、新しい :doc:`フォームバリデーション(検証)クラス
<../libraries/form_validation>` が導入されますので、 それに伴い古いバ
リデーションライブラリは非推奨となります。現在稼動しているアプリケーシ
ョンとの互換性を考慮し、古いライブラリも残してありますが、 出来るだけ
早く新しいバージョンに乗り換えられる事をおすすめします。新しいライブラ
リは従来のものと若干異なった挙動で、いくつかの新機能も備えていますので
、ユーザガイドを注意して読んでください。



ステップ 4: ユーザガイドを更新します。
======================================

ローカルにあるユーザガイドを、画像ファイルを含めて新しいバージョンのも
ので置き換えます。

