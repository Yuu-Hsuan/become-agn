## 環境名稱:smac
##[來源](https://github.com/Taiyopen/IRIS_SMAC_Tutorial/blob/master/README.md)

### 1. Anaconda
使用anaconda 建構新環境，python版本為`3.10.14`
```bash
conda create -n smac python=3.10.14
```
激活環境
```bash
conda activate smac
```

### 2. 安裝SMAC
```bash
pip install git+https://github.com/gingkg/smac.git
```

### 3. 安裝CUDA 11.7
https://developer.nvidia.com/cuda-11-7-0-download-archive

### 4. 安裝pytorch 1.X
```bash
pip install torch==1.13.1+cu117 torchvision==0.14.1+cu117 torchaudio==0.13.1 --extra-index-url https://download.pytorch.org/whl/cu117
```

### 5. 安裝星海爭霸II主程式
使用暴雪官方登入器安裝
https://tw.shop.battle.net/zh-tw

### 6. 下載pymarl主程式
``` bash
git clone https://github.com/gingkg/pymarl.git
```

### 7. 安裝其他依賴項
```bash
pip install sacred pyyaml tensorboard_logger cloudpickle protobuf==3.20.1
```

### 8. 下載SMAC地圖至StarCraft資料夾
地圖下載https://github.com/oxwhirl/smac/releases/tag/v1

放入`~/StarCraft II/Maps/`

資料夾怎麼找到，看[這裡](https://github.com/Yuu-Hsuan/become-agn/blob/main/SC/%E6%89%BEStarCraft%20II%20%E8%A2%AB%E5%AD%98%E5%9C%A8%E5%93%AA%E8%A3%A1.md)

一般情況下需要再創一個`Maps`的資料夾放入即可


### 9. 更改Numpy和scipy版本
因為原本的版本太新(我看是numpy-1.26.4)，會出現`module 'numpy' has no attribute 'bool'.`，

而scipy 1.14.1需要numpy<2.3,>=1.23.5
```bash
python -m pip uninstall numpy scipy
python -m pip install numpy==1.23.1 scipy==1.13
```
