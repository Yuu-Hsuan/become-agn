# PySC2（DeepMind 提供的 StarCraft II 強化學習框架） 
### 1.安裝 StarCraft II
從 Blizzard 官方下載 StarCraft II 安裝包，確保安裝完成後包含以下內容：
* StarCraft II 核心遊戲文件
* Linux 專用版本：可以從 Blizzard SC2 GitHub 獲取
* 安裝後記下遊戲的安裝目錄路徑

### 2.Python 環境
* 建議使用 Python 3.7+。
* 創建虛擬環境：
```
python3 -m venv pysc2_env
source pysc2_env/bin/activate  # Linux/macOS
pysc2_env\Scripts\activate    # Windows
```

### 3.安裝 PySC2
PySC2 是 DeepMind 的官方包，提供與 StarCraft II 的交互功能
* 使用 pip 安裝：
```
pip install pysc2
```
* 依賴項包括：
  * `absl-py`（用於命令行參數處理）
  * `numpy`（數據處理）
  * `protobuf`（處理 SC2 的通信協議）
    
### 4.必要的地圖文件
PySC2 需要額外的地圖包來運行自定義的 StarCraft II 小遊戲：
* 從[PySC2 地圖倉庫](https://github.com/google-deepmind/pysc2/releases)下載地圖文件
* 解壓並放置到 `StarCraftII/Maps/` 目錄下

### 5.GPU 支援
* 如果計算量大（例如使用深度神經網絡進行強化學習），建議使用帶 CUDA 支持的 GPU
* 安裝 GPU 驅動和 CUDA Toolkit：
  * 驅動程序：[NVIDIA 驅動](https://www.nvidia.com/en-us/drivers/)
  * CUDA Toolkit：[CUDA 開發者工具](https://developer.nvidia.com/cuda-downloads)
  * 安裝深度學習框架（如 PyTorch 或 TensorFlow）支持 GPU 計算

### 6.測試安裝
運行以下命令測試 PySC2 是否正確安裝：
```
python -m pysc2.bin.agent --map MoveToBeacon
```
若地圖能正常載入並執行，環境設置成功

### 工具推薦
* Jupyter Notebook：便於可視化訓練過程
* 版本管理工具：如 `git`，管理代碼和實驗過程
