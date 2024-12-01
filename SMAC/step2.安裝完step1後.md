#設置地圖路徑
1. 進入Anaconda prompt
   
   進入python環境
   輸入:
   ```
   python 
   ```

2. 配置環境變量
   輸入:
    ```
    import os
    os.environ["SC2PATH"] = "C:\\Program Files (x86)\\StarCraft II"
    ```

3. 測試是否可以成功載入地圖
   輸入:
   ```
   from smac.env import StarCraft2Env
   ```
   "3m"為地圖名稱，可替換其他地圖，例如'8m' 等( 各地圖的介紹在:[這裡](https://github.com/Yuu-Hsuan/become-agn/blob/main/SMAC/%E5%90%84%E5%9C%B0%E5%9C%96%E8%B3%87%E8%A8%8A.md) )
   ```
   env = StarCraft2Env(map_name="3m")
   ```
   ```
   # 開啟環境
   env.reset()

   #關閉環境 
   env.close()
   ```
   ```
   exit()  #離開python環境
   ```




