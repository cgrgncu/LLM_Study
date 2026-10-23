# Python 開發基本需求

## 先決條件：全域安裝 Python 直譯器

- 下載連結：https://www.python.org/ftp/python/3.12.7/python-3.12.7-amd64.exe
- 安裝時勾選：
  - Add python.exe to PATH
  - Use admin privileges when installing py.exe
  - Disable path length limit
- 驗證：`python --version` → Python 3.12.7
- 硬碟空間：
  - 直譯器安裝版：約 100-150 MB
  - pip 安裝的套件：另計（requests 約 1 MB、pandas 約 50 MB、torch 約 2 GB）
  - 每個專案 .venv：約 30-50 MB（純標準庫）+ 套件大小

## 專案資料夾結構

```
my-python-project/
├── .venv/              ← 虛擬環境（由全域 Python 建立）
├── src/
│   └── main.py
├── tests/              ← 測試程式碼（可選）
├── backup/             ← 手動備份（取代 Git 版本控制）
├── onedir_exe/         ← PyInstaller --onedir 分發輸出
├── embed_exe/          ← embeddable zip + 腳本分發
├── requirements.txt    ← 依賴清單
└── README.txt          ← 專案說明（可選）
```

## 最小可行環境

- Python 直譯器（python.org 安裝版）
- OpenCode
- venv（內建）
- backup 資料夾（取代 Git）

不需要 Git、IDE、Lint、測試框架，可後期再加。
