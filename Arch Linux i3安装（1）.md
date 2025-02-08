#                                                      Arch Linux i3安装
这是我的Arch Linux安装i3窗口管理器教程（后续还有美化教程）

# 配置完成之后，按$MOD+Shift+r可以快速重启i3wm，如果配置没问题的话，可以看到新的效果了。

# 注：想要i3的所有窗口均可使用中文，需安装nerd-fonts-complete
```
sudo pacman -S nerd-fonts-complete
```

## 又注：安装nerd-fonts-complete字体后，alacritty的字体也会随之改变，则安装woff2-fira-code
```
sudo pacman -S woff2-fira-code`
```
### 安装woff2-fira-code后请在~/.config/alacritty/alacritty.yml里找到fonts:和family:取消注释，在family:后加入Fira Code
#### 保存退出后即可使用

# 安装i3窗口管理器包
> ## 注：i3-gaps已合并在i3-wm中，详见[I3 Arch Wiki](https://wiki.archlinuxcn.org/wiki/I3)
```
sudo pacman -S i3
```

## 安装xinit（启动）
```
sudo pacman -S xorg-xinit xorg-server
```
### 注：xorg-server不可缺，若不安装则无法使用startx来启动i3窗口管理器

```
sudo cp /etc/X11/xinit/xinitrc ~/.xinitrc #复制一份xinitrc文件到home目录
```
```
sudo vim ~/.xinitrc #使用vim编辑~/.xinitrc
```
#### 在~/.xinitrc文件中将最后面的6行删去，并添加：exec i3

## 在登录进入TTY后输入startx以进入i3桌面环境
> [Xinit Arch Wiki](https://wiki.archlinuxcn.org/wiki/Xinit)

# 进入了i3桌面以后，i3会让你配置MOD键（本人建议设置为Windows徽标键）
选择您喜欢的MOD键后，您会发现桌面一片黑暗，这时您需要启动终端（终端建议使用alacritty）
```
$MOD+Enter #此处的MOD为您刚刚设置的MOD键（Alt或Windows徽标键）；以打开终端
```
这时您会发现，打开的并不是刚刚安装好的alacritty，而是一个i3默认的终端，这时您需要：
```
sudo vim ~/.config/i3/config #打开i3配置文件
```
将bindsym $mod+Return exec 后面的删去，加入alacritty
## 这时您会发现，自己配置好了，但是使用了快捷键还是打开i3的默认终端，这时您需要按住：
`$MOD+Shift+r`以就地重启i3窗口管理器
这时您就可以开始使用alacritty了

# **BY PILIHU**
# **允许二次修改，开放**
# **若有错误处请指出，联系作者：**
## **QQ：2812167783**
