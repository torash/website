jubaconfig
==========

Synopsis
--------------------------------------------------

.. code-block:: shell

  jubaconfig --cmd <command> [options ...]

Description
--------------------------------------------------

``jubaconfig`` は分散環境において、ZooKeeper に配置される Jubatus サーバの設定ファイルを管理するためのコマンドである。

Options
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* ``[]`` はデフォルト値を意味する。
* ``<zookeeper_list>`` は ZooKeeper サーバの ``ホスト:ポート`` をカンマで区切ったものである (例: ``10.0.0.1:2181,10.0.0.2:2181,10.0.0.3:2181``)。
  値の中にスペースを含めることはできない。
  ZooKeeper が 1 台のみの構成の場合は、カンマを含めず単に ``ホスト:ポート`` を指定する (例: ``10.0.0.1:2181``)。

.. program:: jubaconfig

.. option:: -c <command>, --cmd <command>

   実行したい操作を指定する。
   ``<command>`` の値は以下のいずれかを指定する。

   ========= =====================================================================================
   コマンド  説明
   ========= =====================================================================================
   write     ローカルファイルシステム上の設定ファイルを ZooKeeper 上に登録する
   read      ZooKeeper 上に登録された設定ファイルの内容を表示する
   delete    ZooKeeper 上に登録された設定ファイルを削除する
   list      ZooKeeper 上に登録された設定ファイルの一覧を表示する
   ========= =====================================================================================

.. option:: -f <file>, --file <file>

   ZooKeeper に登録する設定ファイルのパスを指定する。

   ``--cmd write`` を指定した場合のみ有効である。

.. option:: -t <type>, --type <type>

   サーバプログラムの種類 (例: ``classifier``, ``recommender``, ...)。

   ``--cmd write``, ``--cmd read``, ``--cmd delete`` のいずれかを指定した場合のみ有効である。

.. option:: -n <name>, --name <name>

   インスタンス名 (タスクを識別する ZooKeeper クラスタ内でユニークな名前)。

   ``--cmd write``, ``--cmd read``, ``--cmd delete`` のいずれかを指定した場合のみ有効である。

.. option:: -z <zookeeper_list>, --zookeeper <zookeeper_list>

   ZooKeeper サーバの一覧。

   指定されない場合は、環境変数 ``ZK`` が使用される。

.. option:: -d, --debug

   このオプションは廃止されたため使用されない。

.. option:: -?, --help

   このコマンドの簡単な使い方を表示する。
