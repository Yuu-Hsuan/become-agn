

# 有SMAC與PYSC2

## SMAC
  
* 研究進度 : 打開了map

* 架設環境到打開地圖
  1. step1 :
  
     又分為電腦是否有配置nvidia 顯卡
     
     請依據你的電腦是否有顯卡進行選擇
     
     1. [有顯卡](https://github.com/Yuu-Hsuan/become-agn/blob/main/SMAC/step1.IRIS%E7%92%B0%E5%A2%83%E5%89%8D(%E6%9C%89%E9%A1%AF%E5%8D%A1).md)
     2. [無顯卡](https://github.com/Yuu-Hsuan/become-agn/blob/main/SMAC/step1.IRIS%E7%92%B0%E5%A2%83%E5%89%8D(%E7%84%A1%E9%A1%AF%E5%8D%A1).md)(是窮逼也沒關係)


  2. step2 :
     激活虛擬環境，在虛擬環境中輸入地圖位置，並打開地圖。請按[這裡](https://github.com/Yuu-Hsuan/become-agn/blob/main/SMAC/%E5%BE%8C.md)

     p.s.每張地圖有不同的我方和敵方數量，標示在:[各地圖資訊](https://github.com/Yuu-Hsuan/become-agn/blob/main/SMAC/%E5%90%84%E5%9C%B0%E5%9C%96%E8%B3%87%E8%A8%8A.md)
     
## Pysc2 
資料夾中有 `"SC2-RL"`和 `"othearticle"`

* ["pysc2"](https://github.com/google-deepmind/pysc2?tab=readme-ov-file#pysc2---starcraft-ii-learning-environment)為`SC2-RL`資料夾中的開源:

  此專案已成功套用reinforcement learning，可套用多個應用，例如:cmo、starcraft等等，目前github中有關的專案都是引用此專案

* ["SC2-RL"](https://github.com/nicoladainese96/SC2-RL):

  成功將"pysc2"應用在starcraft


* 2024/12/15 研究進度 : 
  * 已大致構想出要怎麼把`Pysc2`變成如同`SMAC`一樣完善
  * 已找到相關開源可參考
  * 欲找到變更pysc2環境參數的辦法
    
1. 方法 :
   [使用靈活的框架](https://github.com/google-deepmind/pysc2?tab=readme-ov-file#pysc2---starcraft-ii-learning-environment)
   允許集成自定義模型（AGN）處理來自StarCraft II的地圖觀測數據和特徵
   
3. 概述:

    (之後寫)
     
3. 是偏向 小遊戲 的套件
