# Rust 開發基本需求

## 先決條件：全域安裝 Rust

- 安裝命令：rustup-init.exe（https://rustup.rs/）
- 建議版本：stable（rustup 預設）
- 驗證：`rustc --version` → rustc 1.82.0
- 硬碟空間：
  - 工具鏈：約 1-2 GB
  - target/：另計（視專案而定，約 100 MB-2 GB）

## 專案資料夾結構

```
my-rust-project/
├── Cargo.toml          ← 專案定義（記錄依賴版本，有助追蹤與重建環境）
├── Cargo.lock          ← 依賴 hash 鎖定
├── build.rs            ← 圖示設定（winres crate）
├── src/
│   ├── main.rs         ← 原始碼入口（慣例使用 main.rs 作為固定名稱）
│   └── lib.rs          ← 函式庫（可選）
├── vendor/             ← 所有依賴 crate（離線編譯用；完全離線、可分發；遵守來源版權）
│   ├── crates.io-*/
│   └── config.toml
├── icon/
│   └── app.ico         ← 應用程式圖示
├── target/
│   └── release/
│       └── app.exe     ← 編譯後的執行檔（直接分發此檔案）
├── backup/             ← 手動備份（取代 Git）
└── README.txt          ← 專案說明（可選）
```

## 最小可行環境

- Rust 工具鏈（rustup 安裝版）
- OpenCode
- Cargo（內建，不需額外安裝）

不需要 Git、IDE、Lint、測試框架，可後期再加。
