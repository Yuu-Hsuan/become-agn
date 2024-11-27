
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

10. 更改Numpy和scipy版本
    ```
    python -m pip uninstall numpy scipy
    ```
    ```
    python -m pip install numpy==1.23.1 scipy==1.13
    ```
