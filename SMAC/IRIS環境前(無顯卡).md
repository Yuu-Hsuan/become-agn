
1. 架設環境
   ```
   conda create -n smac python=3.10.14
   ```

2. 激活環境
   ```
   conda activate smac
   ```
   
3. 安裝SMAC
   ```
   pip install git+https://github.com/gingkg/smac.git
   ```

4. 安裝 CUDA 11.7
   ```
   conda install cudatoolkit=11.8
   ```

5. 安裝 PyTorch(較久)
   ```
   conda install pytorch torchvision torchaudio pytorch-cuda=11.8 -c pytorch -c nvidia
   ```
6. 下載StarCraft II的 Battle net :

   https://tw.shop.battle.net/zh-tw

7. 下載pymarl主程式
   ```
   git clone https://github.com/gingkg/pymarl.git
   ```
   
8. 安裝其他依賴項
   ```
   pip install sacred pyyaml tensorboard_logger cloudpickle protobuf==3.20.1
   ```

9. 下載SMAC地圖至StarCraft資料夾
   地圖下載(https://github.com/oxwhirl/smac/releases/tag/v1)
   
   放入`~/StarCraft II/Maps/`

   資料夾怎麼找到，看[這裡](https://github.com/Yuu-Hsuan/become-agn/blob/main/SC/%E6%89%BEStarCraft%20II%20%E8%A2%AB%E5%AD%98%E5%9C%A8%E5%93%AA%E8%A3%A1.md)

   一般情況下需要再創一個`Maps`的資料夾放入即可

11. 更改Numpy和scipy版本
    ```
    python -m pip uninstall numpy scipy
    ```
    ```
    python -m pip install numpy==1.23.1 scipy==1.13
    ```
