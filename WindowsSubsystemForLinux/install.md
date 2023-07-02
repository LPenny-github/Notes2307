# Install


### 安裝心得

1. 新版安裝步驟只有一行 PowerShell 指令：

    ```PowerShell
        wsl --install
    ```

    * 如果這行指令不成功，建議查閱疑難排解後，使用舊版安裝步驟。這樣最省時間。

2. 開啟 WSL 和 虛擬平台 功能，(除了下 PowerShell 指令外) 可以使用圖形化介面手動開啟，建議設定完後重開機：
    * Settings > Apps > Optional features > More Windows features 
        - [x] Virtual Machine Platform
        - [x] Windows Subsystem for Linux


## 安裝步驟

* 新版
    * 使用 WSL 在 Windows 上安裝 Linux
        * https://learn.microsoft.com/zh-tw/windows/wsl/install

* 舊版
    * 舊版 WSL 的手動安裝步驟
        * https://learn.microsoft.com/zh-tw/windows/wsl/install-manual


## 疑難排解

* 針對適用於 Linux 的 Windows 子系統進行疑難排解
    * https://learn.microsoft.com/zh-tw/windows/wsl/troubleshooting