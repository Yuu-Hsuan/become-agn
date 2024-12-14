## 方法(只是構想；尚未實踐)

### 1. 封裝高層次操作：新增如「自動移動」「自動攻擊」的接口，減少操作細節負擔

問題：

PySC2 的動作是低層次的，比如選擇單位並指定目標位置，還需要手動處理座標計算和技能細節，對 AI 訓練來說非常繁瑣


改進方法：
* 封裝常見動作為高層次接口：
  
1. 移動到目標位置
   * 目前需要指定座標和具體移動命令，可將其封裝為：
   * python
     ```
     def move_to(unit_id, target_position):
     # 指定單位移動到目標座標
     return FunctionCall(MOVE_SCREEN, [unit_id, target_position])
     ```
     這樣使用者只需要提供角色和目標位置，底層會自動處理

2. 自動攻擊敵人
   * 讓角色自動選擇最近的敵人並攻擊：
   * python
     ```
     def auto_attack(unit_id, enemy_units):
     # 選擇最近敵人
     target = find_closest_enemy(unit_id, enemy_units)
     return FunctionCall(ATTACK_SCREEN, [unit_id, target.position])
     ```
     這樣使用者只需告訴角色「攻擊」，不必指定細節

* 提供預設動作模板：
  
  在 PySC2 的基礎上，實現一些高層次的行為模板，比如「巡邏」、「攻擊並撤退」等，讓使用者可以快速使用
   
### 2. 簡化動作空間：將繁瑣的細節整合為幾個高層次動作，方便 AI 訓練

問題：

PySC2 的動作空間非常大，AI 必須學習細化的行為（如點擊具體座標），這對策略學習來說是多餘的負擔

改進方法：
* 分層設計動作空間：
  * 低層次動作：保留詳細操作以支持進階研究（如移動到具體座標）
  * 高層次動作：提供預設行為選項，如：
    1. 「向北移動」、「向南移動」——簡化為方向指令。
    2. 「攻擊最近敵人」、「撤退到基地」——簡化為策略指令。
       
* 修改環境中的動作接口：
  
  重寫 PySC2 的動作生成部分，在環境中引入簡化的高層次動作，具體步驟：

  1. 定義動作選項，例如 `["move_north", "move_south", "attack_nearest"]`
  2. 將這些高層次選項翻譯成 PySC2 的低層次指令，在底層執行

### 3. 內建路徑規劃和避障功能：讓角色智能地移動到目標位置

問題：

目前在 PySC2 中，角色的移動需要使用者自己設計路徑規劃（如避開障礙物），這對 AI 訓練增加了不必要的難度。

改進方法：
* 內建路徑規劃算法：
  使用 A* 或其他路徑規劃算法，讓角色自動找到從當前位置到目標位置的最短路徑，並封裝為高層次接口。

  * 新增功能，例：
  * python
    ```
    def navigate_to(unit_id, target_position, game_map):
       path = find_path(current_position, target_position, game_map)
       for step in path:
           execute_move(unit_id, step)
    ```
  * 動態避障功能：
    
    如果移動過程中遇到敵人或障礙物，系統能自動計算繞開路徑，讓角色能智能地到達目標

  * 內建工具庫
    
    提供如 `find_path`、`find_closest_enemy` 等工具函數，供使用者輕鬆構建更複雜的操作

### 4. 新增內建場景和初始化工具：標準化環境設計，提供多樣化挑戰場景

問題：

PySC2 沒有內建標準化的場景，使用者需要自行設計環境（如放置敵人、設定資源），增加了學習門檻。

改進方法：
* 新增場景 API：
  提供一系列標準化的場景配置接口，讓用戶快速生成訓練環境

  如：
  python
  ```
  def create_resource_collection_scene(map_size, num_resources):
    # 設置場景大小與資源數量
    return generate_map(map_size, resources=num_resources)
  ```
  
* 內建場景庫
  
  設計幾個常用場景，讓 AI 能快速上手：
  1. 資源收集場景： 單個角色學會找到最近的資源並收集
  2. 生存挑戰場景： 敵人持續追蹤角色，角色需學會逃跑或自衛
  3. 敵人擊殺場景： 單角色挑戰多個敵人
  
* 自定義初始化功能：
  
  用戶可以指定角色初始位置、敵人數量、地圖障礙等

