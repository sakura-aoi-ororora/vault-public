# add_mlir_dialect(dialect_name,dialect_namespace)
* 第一引数がフォルダ内のtblgenファイルの名前(拡張子なし)
	* 大体は~Opsが指定されてる
	* どうやら~Dialectも~Typesも~Opsでincludeしているらしい(=全部のデータをTablegenできる)
	* なおパスはまた別らしい
* 第二引数が名前空間(?)
# add_mlir_doc(tblgen_file_name,doc_file_name,doc_directory,(auguments))
- そのまま
- mlir_docターゲットができて､それをビルドするとbuild/docにドキュメントができる
- 生成に使ってるのはHugo?らしい
- augumentsは[これらしい](https://llvm.org/docs/CommandGuide/tblgen.html#mlir-tblgen-options)(~docとかのやつをつける)
# 注意点
- 使うには`cmake_minimum_required(VERSION 3.20.0)`が必要
	- ないとエラーが出る
- tblgenの`include`では`include_directories()`の指定から持ってくる