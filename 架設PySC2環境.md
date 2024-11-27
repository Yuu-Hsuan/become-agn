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
