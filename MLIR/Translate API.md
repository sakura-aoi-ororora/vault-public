#MLIR
# What's This?
- LLVM IRとかに変換するやつ
- 'emitc'とか色々ある
- MLIR内ではTargetとか書かれている
# 参考リンク
- https://github.com/llvm/llvm-project/blob/main/mlir/lib/Target/Cpp/TranslateToCpp.cpp
	- emitcのやつ
	- C++に変換する
	- 参考になる､､､かな?
- https://github.com/llvm/llvm-project/blob/main/mlir/lib/Target/Cpp/TranslateRegistration.cpp
	- レジスタ登録部分
	- TranslateFromMLIRRegistrationを使うらしい
		- 第一､第二引数は(コマンドライン上のオプション名,説明)
		- 第三引数はMLIR上のトップの命令(ModuleOpっぽい)に対して実行される関数
		- 第四引数はレジスタに登録するやつ
			- registory.insert<>で使用できる方言を指定するみたい
			- 他にもやってそうだけどLLVMIRTargetも確認必須かな
	- mlir-translateでは登録する関数を呼び出しているらしい