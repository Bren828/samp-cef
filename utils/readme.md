`wrapper.h`: генерация биндингов для CEF

запускать из папки релиза CEF (либо в `-I` указать путь до нее)

Generate the Windows x86 C API bindings from the pinned distribution:

```powershell
$env:CEF_PATH = (Resolve-Path third_party/cef)
$env:LIBCLANG_PATH = "C:/path/to/llvm/bin"
cargo install bindgen-cli --version 0.72.1 --locked
node scripts/generate-cef-bindings.mjs
```

The generator selects stable `CEF_API_VERSION` 15000 from `cef-distribution.json` and normalizes CEF callbacks to Rust's Windows `system` ABI.
