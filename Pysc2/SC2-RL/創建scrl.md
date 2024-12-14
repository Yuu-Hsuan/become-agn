# 環境名稱:scrl
##[來源](https://github.com/nicoladainese96/SC2-RL)
DQN 的概念

## 從環境架設到在遊戲上執行

### 1. 建立並配置虛擬環境

1. 使用anaconda prompt 建構新環境，python版本為`3.8`
   ```bash
   conda create -n scrl python=3.8 -y
   ```
   
2. 啟用虛擬環境
   ```bash
   conda activate scrl
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
   
2. 安裝相依套件 :
   * ```
     pip install numpy tensorflow pysc2 matplotlib
     ```
   * 執行以下指令確認套件是否正確安裝 : 應該會看到剛剛安裝的套件，例如 `numpy`、`tensorflow` 等列在清單中
     ```
     pip list
     ```

   * 安裝 PyTorch
     ```
     conda install pytorch torchvision torchaudio -c pytorch
     ```

   * 完善資料中的`ConvLSTM_pytorch`檔案
     1. 將[這個](https://github.com/ndrplz/ConvLSTM_pytorch)下載至`ConvLSTM_pytorch`資料夾
     2. 輸入`python`進入python
        ```
        import sys
        import os
        sys.path.append(os.path.join(os.getcwd(), 'ConvLSTM_pytorch'))
        exit()

   * 降級版本
     降級 protobuf 套件到 3.20.x 或更低版本
     ```
     pip install protobuf==3.20.*
     ```

     
   
   
4. 配置 StarCraft II 環境
   
   * 安裝 StarCraft II（SC2）遊戲，前往 Blizzard 官網 下載
     
   * 下載 SC2 API 和地圖檔
     1. 指向資料夾
        ```
        mkdir C:\Program Files (x86)\StarCraft II\Maps
        ```
     2. 下載[mini_games.zip](https://github.com/deepmind/pysc2/releases/download/v1.2/mini_games.zip)
     3. 將`mini_games.zip`解壓縮到 `C:\Program Files (x86)\StarCraft II\Maps`
     4. 進入Python : 輸入`python`來指定地圖路徑
        ```
        MAPS_PATH = "C:\\Program Files (x86)\\StarCraft II\\Maps"
        ```
        完成地圖配置後，回到專案根目錄運行程式：
        ```
        exit()
        ```
     
     
### 3. 運行程式

1. 啟動程式 在專案目錄下執行以下指令：
   ```
   python run.py
   ```
2. 檢查輸出 : 如果程式成功運行，應該會啟動 SC2 並執行相關操作或訓練模型


## 修改內部參數方法
加油加油



