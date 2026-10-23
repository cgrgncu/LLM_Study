# Go 開發基本需求

## 先決條件：全域安裝 Go

- 下載連結：https://go.dev/dl/go1.23.4.windows-amd64.msi
- 安裝時勾選：Add to PATH（預設勾選）
- 驗證：`go version` → go1.23.4 windows/amd64
- 硬碟空間：
  - 直譯器安裝版：約 150-200 MB
  - GOPATH/cache：另計（視依賴而定，約 100-500 MB）
  - 編譯後 .exe：約 5-20 MB（單一執行檔）

## 專案資料夾結構

```
my-go-project/
├── src/
│   ├── main.go         ← 原始碼入口（慣例使用 main.go 作為固定名稱）
│   ├── go.mod          ← 模組定義（記錄套件版本，有助追蹤與重建環境）
│   ├── go.sum          ← 依賴 hash 鎖定（vendor 時產生）
│   ├── vendor/         ← 所有依賴原始碼（離線編譯用；完全離線、可分發；遵守來源版權）
│   │   ├── github.com/
│   │   └── modules.txt
│   └── rsrc.syso       ← 資源檔（圖示等）
├── icon/
│   └── app.ico         ← 應用程式圖示
├── exe/
│   └── app.exe         ← 編譯後的執行檔
├── build.bat           ← 編譯腳本
├── backup/             ← 手動備份（取代 Git）
└── README.txt          ← 專案說明（可選）
```

## 最小可行環境

- Go 直譯器（go.dev 安裝版）
- OpenCode
- Go Modules（內建，不需額外安裝）

不需要 Git、IDE、Lint、測試框架，可後期再加。
