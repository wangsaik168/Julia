#### 准备工作

```bash
git config --global user.email "wangsaift@163.com"
git config --global user.name "wangsaik168"
git config --global credential.helper "/mnt/c/Program\ Files/Git/mingw64/libexec/git-core/git-credential-wincred.exe"
```

#### 开始安装

##### 1.安装关键dependencies

```bash
cd ~
sudo apt update
sudo apt-get upgrade
sudo apt install make gcc unzip
sudo apt-get update
sudo apt-get install libxt6 libxrender1 libgl1-mesa-glx libqt5widgets5 
```

##### 2.安装conda

下载https://repo.anaconda.com/archive/Anaconda3-2020.07-Linux-x86_64.sh，复制到ubuntu根目录

```bash
安装：bash Anaconda3-2020.07-Linux-x86_64.sh
```

重启terminal

删除安装文件：

```bash
pip install --upgrade --force-reinstall pyzmq
rm Anaconda3-2020.07-Linux-x86_64.sh
```

##### 3.安装julia

下载https://julialang-s3.julialang.org/bin/linux/x64/1.5/julia-1.5.1-linux-x86_64.tar.gz，复制到根目录

```bash
安装：tar xzvf julia-1.5.1-linux-x86_64.tar.gz
```

使用记事本打开  .bashrc   

在最后添加：export PATH=~/julia-1.5.1/bin:$PATH

```bash
运行：source .bashrc
```

输入Julia，会显示出Julia的运行界面REPL。

##### 4.安装jupinx,deps

```bash
conda upgrade conda
conda install dask distributed
pip install jupinx sphinxcontrib.bibtex jupinx guzzle_sphinx_theme
```

##### 5.配置jupyter

生成配置文件：

```
jupyter-notebook --generate-config
```

记事本打开该文件，然后修改如下命令，并将#去掉：

```
c.NotebookApp.open_browser = False
c.NotebookApp.token = ''
c.NotebookApp.port = 8888
```

在vs code中输入：jupyter notebook，点击“follow link”，系统浏览器会自动打开notebook网站

##### 6.julia的包镜像更改为国内镜像

```
] add JuliaZH
using JuliaZH
JuliaZH.generate_startup("default")
JuliaZH.generate_startup("BFSU")  ##永久更改为国内pkg镜像
```







