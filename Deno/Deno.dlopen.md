# What's "Deno.dlopen"?
DenoでFFIをするための関数｡
簡単...だと思う｡

# コード例

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
		parameters: ["i32", "i32"], result: "i32"
	}
})

const result = lib.symbols.add(5,10); // 15
console.log(result) // 15

```

```bash
deno run --allow-ffi --unstable ffi.ts
```
# ハマりやすいポイント

* `--allow-ffi --unstable`が必須
	* 無いと意味不明なえ