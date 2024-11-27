# 使用 Anaconda 架設好 Python 環境後，可以按照以下步驟將 GitHub 上的程式碼載入並執行
### 1.確認環境安裝完成
首先確保您的 Anaconda 環境已正確安裝並啟動：
1. 創建新的虛擬環境（可選）：
```
conda create -n pysc2_env python=3.8
conda activate pysc2_env
```
2. 安裝必要的依賴，例如 pysc2：
```
pip install pysc2
```
 ### 2.下載 GitHub 程式碼
1. 使用 Git 克隆專案
如果未安裝 `git`，請先安裝它（Anaconda 默認應該已包含）。然後執行以下命令克隆 GitHub 專案到本地：
```
git clone <GitHub 專案網址>
cd <專案目錄>
```
例如，對於 PySC2 強化學習代理程式碼：
```
git clone https://github.com/deepmind/pysc2.git
cd pysc2
```
2. 手動下載
若無法使用 Git，可以直接到 GitHub 頁面，點擊右上方的 "Code" 按鈕並選擇 "Download ZIP"，然後解壓到目標目錄
