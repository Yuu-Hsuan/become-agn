#
1. 確認 StarCraft II 的安裝目錄 : `C:\Program Files (x86)\StarCraft II`
2. 將地圖文件放入正確的目錄
   1. 確保以下目錄結構存在：
      ```
      StarCraft II/Maps/SMAC_Maps
      ```
      
   2. 將地圖文件放入此目錄 :
      ```
      C:\Program Files (x86)\StarCraft II\Maps\SMAC_Maps
      ```
      
3. 設置地圖路徑（Python 代碼）
   ```
   python  #進入python
   ```

   在運行 SMAC 代碼時，要指定 StarCraft II 的路徑，以便環境能夠找到地圖文件

   配置環境變量：Python 代碼中設置
    ```
    import os
    os.environ["SC2PATH"] = "C:\\Program Files (x86)\\StarCraft II"
    ```
5. 測試地圖加載

   在 Python 中運行以下代碼以測試是否可以成功載入地圖：
   ```
   from smac.env import StarCraft2Env
   
   # 替換為地圖名稱，如 '3m'、'8m' 等
   env = StarCraft2Env(map_name="3m")

   # 開啟
   env.reset()
   
   print("地圖加載成功")
   
   env.close()
   ```
   ```
   exit()  #離開python
   ```




