# add_mlir_dialect(dialect_name,dialect_namespace)
* 第一引数がフォルダ内のtblgenファイルの名前(拡張子なし)
	* 大体は~Opsが指定されてる
	* どうやら~Dialectも~Typesも~Opsでincludeしているらしい(=全部のデータをTablegenできる)
	* なおパスはまた別らしい
* 第二引数が名前空間(?)