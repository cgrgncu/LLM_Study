# Lazarus 開發基本需求

## 先決條件：全域安裝 Lazarus

- 下載連結：https://www.lazarus-ide.org/
- 建議版本：Lazarus 3.6（含 Free Pascal 3.2.2）
- Windows 安裝檔範例：lazarus-3.6-fpc-3.2.2-win64.exe
- 驗證：開啟 Lazarus IDE → Help → About
- 硬碟空間：
  - IDE + FPC：約 500 MB-1 GB
  - 編譯後 .exe：約 2-10 MB

## 專案資料夾結構

```
my-lazarus-project/
├── project1.lpr        ← 主程式入口（Lazarus Project，IDE 自動產生）
├── project1.lpi        ← 專案資訊（IDE 設定）
├── project1.lps        ← IDE 狀態（IDE 自動產生）
├── project1.res        ← 資源檔（圖示等）
├── project1.ico        ← 應用程式圖示
├── project1.exe        ← 編譯後的執行檔（預設輸出在同目錄）
├── unit1.pas           ← 單元（表單/邏輯）
├── unit1.lfm           ← 表單設計檔（IDE 自動產生）
├── lib/                ← 編譯中間檔（IDE 自動產生）
│   └── x86_64-win64/
│       ├── project1.compiled
│       ├── project1.o
│       ├── project1.obj
│       ├── project1.res
│       ├── unit1.lfm
│       ├── unit1.o
│       └── unit1.ppu
├── backup/             ← 手動備份（取代 Git）
└── README.txt          ← 專案說明（可選）
```

## 最小可行環境

- Lazarus IDE（含 Free Pascal）
- OpenCode
- 內建編譯器（不需額外安裝）

不需要 Git、IDE、Lint、測試框架，可後期再加。
