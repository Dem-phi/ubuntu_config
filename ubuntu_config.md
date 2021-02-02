[toc]
# ubuntu config
by Demphi
## 更换source
```bash
# 首先备份源列表
sudo cp /etc/apt/sources.list /etc/apt/sources.list_backup
# 权限
sudo chmod 777 /etc/apt/sources.list
# 打开sources.list文件
sudo gedit /etc/apt/sources.list
# 阿里源
deb http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
# 刷新lists
sudo apt-get upgrade
sudo apt-get install build-essential文件
# 注意事项

```



## google-chrome
```bash
sudo wget http://www.linuxidc.com/files/repo/google-chrome.list -P /etc/apt/sources.list.d/
wget -q -O - https://dl.google.com/linux/linux_signing_key.pub  | sudo apt-key add -
sudo apt update
sudo apt install google-chrome-stable
```

## vscode
downloads .deb 
sudo dpkg -i *.deb

### install 插件

ROS

koroFileHeader

Material Theme

Chinese



## zsh oh-my-zsh auto-suggestion
```bash
sudo apt-get install zsh
# installl oh-my-zsh and auto-suggestion
sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)" 或者$ sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
git clone git://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
# 修改 .zshrc
# my theme is "af-magic"
plugins=(
 git
 zsh-autosuggestions
 zsh-syntax-highlighting
)
# add some shortcuts
alias szs="source ~/.zshrc"
alias sss="source devel/setup.zsh"
alias ezs="gedit ~/.zshrc"
# source
sss	或者
source ~/.zshrc
```



## ranger/tree and neofetch 

```bash
sudo apt-get install neofetch
sudo apt-get install ranger
```



## gnome-tweak-tool

```bash
sudo apt-get install gnome-shell         #安装gnome桌面窗口管理程序
sudo apt install gnome-tweak-tool        #安装管理工具
sudo apt install gnome-shell-extensions  #扩展管理
```

theme: /usr/share/themes 自己使用的是OSX-Arc-Shadow
icons: /usr/share/icons  自己使用的是Numix-Circle
shell: 

link:https://github.com/asd2003asd/OSX-Arc-Shadow



## Terminator

### Install
sudo apt install terminator
### config

```cpp
[global_config]
  title_transmit_bg_color = "#d30102"
  focus = system
  suppress_multiple_term_dialog = True
[keybindings]
[profiles]
  [[default]]
    palette = "#2d2d2d:#f2777a:#99cc99:#ffcc66:#6699cc:#cc99cc:#66cccc:#d3d0c8:#747369:#f2777a:#99cc99:#ffcc66:#6699cc:#cc99cc:#66cccc:#f2f0ec"
    background_color = "#2D2D2D" # 背景颜色
    background_image = None
    background_darkness = 0.85
    cursor_color = "#2D2D2D" # 光标颜色
    cursor_blink = True # 光标是否闪烁
    foreground_color = "#EEE9E9" # 文字的颜色
    use_system_font = False # 是否启用系统字体
    font = Ubuntu Mono 13  # 字体设置，后面的数字表示字体大小
    copy_on_selection = True # 选择文本时同时将数据拷贝到剪切板中
    show_titlebar = False # 不显示标题栏，也就是 terminator 中那个默认的红色的标题栏
[layouts]
  [[default]]
    [[[child1]]]
      type = Terminal
      parent = window0
      profile = default
    [[[window0]]]
      type = Window
      parent = ""
[plugins]
```

config 之后 需要执行 source .zshrc



##  NVIDIA驱动(16.04 多屏幕/ 18.04)
### 16.04

更换驱动


### 18.04
```bash
sudo add-apt-repository ppa:graphics-drivers/ppa
sudo apt-get update
```



## V2ray and QV2ray
```bash
git clone https://github.com/Dem-phi/v2ray-and-Qv2ray.git
sudo chmod +x ./Qv2ray-refs.tags.v1.99.6-linux.AppImage
./Qv2ray-refs.tags.v1.99.6-linux.AppImage   
```




## Typora

```bash
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys BA300B7755AFCFAE
# 添加仓库并更新
sudo add-apt-repository 'deb http://typora.io linux/'
sudo apt-get update
# Install
sudo apt-get install typora
```



## aptitude

```bash
sudo apt-get install aptitude
```



## deepin-winest-stm32cubeide_1.3.0_5720_20200220_1053_amd64.deb_bundle.sh 

```bash
git clone https://github.com/wszqkzqk/deepin-wine-ubuntu.git
sudo ./intall.sh	#deepin-wine安装完成
```

qq基本上是用不了,一般用TIM

### TIM

下载对应的软件包 ,会出现TIM显示不料中文的情况
1.下载字体(simsun.ttc)
2.放在对应的文件夹下 /home/demphi/.deepinwine/Deepin-TIM/drive_c/windows/Fonts
3.编写文件zh.reg

```
REGEDIT4
[HKEY_LOCAL_MACHINE\Software\Microsoft\Windows NT\CurrentVersion\FontSubstitutes]
"Arial"="simsun"
"Arial CE,238"="simsun"
"Arial CYR,204"="simsun"
"Arial Greek,161"="simsun"
"Arial TUR,162"="simsun"
"Courier New"="simsun"
"Courier New CE,238"="simsun"
"Courier New CYR,204"="simsun"
"Courier New Greek,161"="simsun"
"Courier New TUR,162"="simsun"
"FixedSys"="simsun"
"Helv"="simsun"
"Helvetica"="simsun"
"MS Sans Serif"="simsun"八十
"MS Shell Dlg"="simsun"
"MS Shell Dlg 2"="simsun"
"System"="simsun"
"Tahoma"="simsun"家
"Times"="simsun"
"Times New Roman CE,238"="simsun"
"Times New Roman CYR,204"="simsun"
"Times New Roman Greek,161"="simsun"
"Times New Roman TUR,162"="simsun"
"Tms Rmn"="simsun"
```

4.在终端中输入 deepin-wine regedit zh.reg

### QQ Music



## stm32cubemx

### JAVA环境

```bash
# STM32CubeMX安装前需要有java环境，因此需要提前安装。
sudo apt-get install default-jre
```

### stlink

```bash

```

### STM32cubeMX

```bash
#下载STM32cubeMX
# http://www.st.com/content/st_com/zh/products/development-tools/software-development-tools/stm32-software-development-tools/stm32-configurators-and-code-generators/stm32cubemx.html
#解压之后有四个文件，打开Readme.html，根据流程安装即可
#installation directory of stm32cubemx is /usr/local/STMicroelectronics/STM32Cube/STM32CubeMX
# run cubeMX
cd /usr/local/STMicroelectronics/STM32Cube/STM32CubeMX
./STM32CubeMX
```

```bash
#可以创建一个bash脚本
#!/bin/sh
### BEGIN INIT INFO
# Provides:          STM32cubeMX.sh
# Required-start:    $local_fs $remote_fs $network $syslog
# Required-Stop:     $local_fs $remote_fs $network $syslog
# Default-Start:     2 3 4 5
# Default-Stop:      0 1 6
# Short-Description: starts the cubeMX
### END INIT INFO

cd /usr/local/STMicroelectronics/STM32Cube/STM32CubeMX
setsid ./STM32CubeMX&

# exit 0
```

### STM32cubeIDE

```bash
#下载STM32cubeIDE
#到st官网下载即可，解压之后打开文件夹
sudo chmod +x st-stm32cubeide_1.5.1_9029_20201210_1234_amd64.deb_bundle.sh
sudo ./st-stm32cubeide_1.5.1_9029_20201210_1234_amd64.deb_bundle.sh
# 耐心按回车（Enter），因为最后会让我们选择接受ST的License，不然的话，会因为我们不接受证书而退出，并提示：License NOT accepted. Not installing software. Hit return to exit.
```



## ubuntu_18.04 demphi

link: https://github.com/Dem-phi/ubuntu_config.git

