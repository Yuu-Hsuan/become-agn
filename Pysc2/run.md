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

### 3.檢查並安裝依賴
通常專案會包含`requirements.txt`或`environment.yml`，記錄了運行所需的依賴項。執行以下命令安裝依賴：

1. 使用`requirements.txt`：
```
pip install -r requirements.txt
```
2. 使用`environment.yml`（如果存在）：
```
conda env update -f environment.yml
conda activate pysc2_env
```
如果專案未提供依賴清單，需要手動查閱 README 文件並安裝相關包，例如：
```
pip install tensorflow gym numpy
```

### 4.設定環境變數
某些 PySC2 專案需要設置 StarCraft II 的安裝路徑，例如：
```
export SC2PATH="/path/to/StarCraftII"
```
在 Windows 系統上，可以使用以下命令：
```
set SC2PATH=C:\Path\To\StarCraftII
```

### 5.運行專案程式
1. 找到專案的主要執行文件，通常是 `.py` 文件（如 `main.py` 或 `run.py`）
2. 執行程式，例如：
```
python main.py --map MoveToBeacon
```
如果專案包含自定義參數，可以參考 README 或程式碼中的解析器部分了解可用選項

### 6.調試與測試
* 確認依賴已安裝：若有錯誤提示缺少某些模組，請根據提示安裝對應包
* 檢查 StarCraft II 環境：確保地圖文件和遊戲引擎正確安裝

### 小提示
* 使用 Anaconda Navigator 的「Jupyter Notebook」或 IDE（如 VS Code、PyCharm）可以更方便地調試程式碼
* 若需修改或擴展程式碼，建議在虛擬環境中測試並保持原始專案的清潔性


