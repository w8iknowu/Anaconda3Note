# Anaconda3相关命令随记
记本次使用的虚拟环境名为**envName**
## 环境的创建/激活/退出/删除

```shell
conda create -n envName python=3.x 
conda activate envName
conda deactivate
conda remove -n envName --all
```

## 查看已有虚拟环境
```shell
conda env list 
conda info --envs
```

## 查看当前环境已安装的包
```shell
conda list 
conda list -n envName #查看环境名为envName下已安装的包
```

## 导出/导入当前环境下已安装的包
```shell
pip freeze > requiremnet.txt
conda env export > requirement.yml 
pip install -r requirement.txt 
conda env create -f requiremnet.yml #创建一个环境，并安装requirement中的包
```

## 复制已有的环境的包，并以此生成新的环境
```shell
conda create -n newEnv --clone oldEnv
```

## 镜像相关
### 临时使用镜像
```shell
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple some-package
# 注意，simple 不能少, 是 https 而不是 http
# https://pypi.tuna.tsinghua.edu.cn/simple
```

### 添加镜像
[本部分来源点我](https://blog.csdn.net/qq_32650831/article/details/127952502)
```shell
conda config --add channels xxxxx


# 添加清华源
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/
 
# 添加阿里云镜像源
conda config --add channels https://mirrors.aliyun.com/anaconda/pkgs/free/
conda config --add channels https://mirrors.aliyun.com/anaconda/pkgs/main/
 
# 添加中科大源
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/pkgs/main/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/conda-forge/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/msys2/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/bioconda/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/menpo/
 
 
 
# 设置搜索时显示通道地址
conda config --set show_channel_urls yes

```

### conda镜像
```shell
channels:
  - defaults
show_channel_urls: true
default_channels:
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/r
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/msys2
custom_channels:
  conda-forge: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  msys2: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  bioconda: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  menpo: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  pytorch: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  simpleitk: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
 
# 即可添加 Anaconda Python 免费仓库。

# 运行 conda clean -i 清除索引缓存，保证用的是镜像站提供的索引。

```