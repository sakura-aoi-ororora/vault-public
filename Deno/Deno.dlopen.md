# What's "Deno.dlopen"?
DenoでFFIをするための関数｡
簡単...だと思う｡

## コード例

詳しくは
https://docs.deno.com/runtime/manual/runtime/ffi_api
を見ると良き｡

```c
// 共有ライブラリ(.so)でコンパイルする
int add(int a, int b) {  
    return a + b;  
}

```

```typescript

const libPath = "path/to/lib.so"

const lib = Deno.dlopen(libPath, {
	add: {
		parameters: ["i32", "i32"], result: "isize"
	}
})

```