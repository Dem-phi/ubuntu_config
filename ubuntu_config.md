[toc]
# ubuntu config
by Demphi
## 更换source
### 命令
##### 首先备份源列表
sudo cp /etc/apt/sources.list /etc/apt/sources.list_backup
##### 权限
sudo chmod 777 /etc/apt/sources.list
##### 打开sources.list文件
sudo gedit /etc/apt/sources.list
##### 阿里源
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
##### 刷新lists
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install build-essential文件

### 注意事项



## google-chrome
sudo wget http://www.linuxidc.com/files/repo/google-chrome.list -P /etc/apt/sources.list.d/
wget -q -O - https://dl.google.com/linux/linux_signing_key.pub  | sudo apt-key add -
sudo apt update
sudo apt install google-chrome-stable



## vscode
downloads .deb 
sudo dpkg -i *.deb
### install 插件

ROS



## zsh oh-my-zsh auto-suggestion
sudo apt-get install zsh
### installl oh-my-zsh and auto-suggestion
sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)" 
git clone git://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
### 修改 .zshrc
plugins=(
  git
  zsh-autosuggestions
  zsh-syntax-highlighting
)
source .zshrc



## ranger/tree and neofetch 
sudo apt-get install neofetch
sudo apt-get install ranger



## gnome-tweak-tool
sudo apt-get install gnome-shell         #安装gnome桌面窗口管理程序
sudo apt install gnome-tweak-tool        #安装管理工具
sudo apt install gnome-shell-extensions  #扩展管理

theme: /usr/share/themes 自己使用的是OSX-Arc-Shadow
icons: /usr/share/icons  自己使用的是Numix-Circle
shell: 



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
sudo add-apt-repository ppa:graphics-drivers/ppa
sudo apt-get update



## V2ray and QV2ray
git clone 
sudo chmod +x ./Qv2ray-refs.tags.v1.99.6-linux.AppImage
./Qv2ray-refs.tags.v1.99.6-linux.AppImage



## Typora
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys BA300B7755AFCFAE
### 添加仓库并更新
sudo add-apt-repository ‘deb http://typora.io linux/’
sudo apt-get update
### Install
sudo apt-get install typora






