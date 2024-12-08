# 環境名稱:scrl
##[來源](https://github.com/nicoladainese96/SC2-RL)

### 1. 建立並配置虛擬環境

1. 使用anaconda prompt 建構新環境，python版本為`3.8`
   ```bash
   conda create -n dscrl python=3.8 -y
   ```
   
2. 啟用虛擬環境
   ```bash
   conda activate dqnsc
   ```

3. 安裝必要工具 : 在虛擬環境中安裝 `git` 和 `pip`
   ```bash
   conda install git -y
   ```

### 2. 下載並配置專案

1. 複製專案
   ```
   git clone https://github.com/nicoladainese96/SC2-RL.git
   cd SC2-RL
   ```
   
2. 安裝相依套件 : 根據專案中的 `requirements.txt` 安裝必要套件
   ```
   pip install -r requirements.txt
   ```
   
3. 配置 StarCraft II 環境
   1. 安裝 StarCraft II（SC2）遊戲，前往 Blizzard 官網 下載
   ```
   pip install -r requirements.txt
   ```
   
### 4. 配置地圖文件
1. 從 SMAC 官方 GitHub 下載地圖文件(https://github.com/oxwhirl/smac/tree/master/smac/env/starcraft2/maps)
2. 將 `.SC2Map` 文件複製到 SC2 地圖目錄

### 5.配置 SC2-RL 並運行遊戲
1. 啟動遊戲測試
    1. 回到 SC2-RL 專案目錄，執行以下命令：
       ```
       python run_main.py
       ```
   2. 這將啟動一個基本的強化學習代理與 SC2 的交互
2. 確認代理運行
   
   運行後，遊戲介面會打開並展示代理如何控制單位進行簡單操作

