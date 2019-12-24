用ubuntu做东西很久了，总结了一些教程，一直想整理一下，确实是没有时间，这下简单的整理了一下，大家可以看看，具体的软件安装包已经推到了本人的github帐号上了，需要下载的可以直接去github下载。如果有什么问题可以直接留言或者去github提issue。下面是分步进行的，指令需要一条执行，由于时间有限，就不写shell脚本了，等以后重新更新的时候把shell脚本写一下。

1.设置源为清华源或者阿里源等国内的源
2.设置分屏：(选做)
    系统设置，屏幕显示，关闭之前的屏幕，只显示最新的屏幕
3.添加搜狗输入法

        chmod +x sousogoupinyin_2.2.0.0108_amd64.deb
        
        sudo dpkg -i sogoupinyin_2.2.0.0108_amd64.deb
        
        sudo apt-get -f install
        
        sudo dpkg -i sogoupinyin_2.2.0.0108_amd64.deb
        
4.安装谷歌浏览器

        sudo wget https://repo.fdzh.org/chrome/google-chrome.list -P /etc/apt/sources.list.d/
     
        wget -q -O - https://dl.google.com/linux/linux_signing_key.pub  | sudo apt-key add -
        
        sudo apt-get update
        
        sudo apt-get install google-chrome-stable
        
5.卸载系统软件
   卸载火狐浏览器
   
        dpkg --get-selections |grep firefox
        
        sudo apt-get purge firefox firefox-locale-en firefox-locale-zh-hans unity-scope-firefoxbookmarks
        
   卸载亚马逊
   
        sudo apt-get remove unity-webapps-common
        
   卸载自带的Word
  
        sudo apt-get remove --purge libreoffice*
        
6.安装福昕PDF阅读

        tar -zxvf FoxitReader.enu.setup.2.4.4.0911.x64.run.tar.gz
        
        sudo ./FoxitReader.enu.setup.2.4.4.0911\(r057d814\).x64.run
        
7.安装WPS和字体 

        sudo dpkg -i wps-office_11.1.0.8392_amd64.deb
        
     安装字体
     
        unzip wps_symbol_fonts.zip
       
        sudo cp mtextra.ttf  symbol.ttf  WEBDINGS.TTF  wingding.ttf  WINGDNG2.ttf  WINGDNG3.ttf  /usr/share/fonts
        
8.安装markdown-typora

        sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys BA300B7755AFCFAE
        
        sudo add-apt-repository 'deb http://typora.io linux/' 
       
        sudo apt-get update
        
        sudo apt-get install typora
        
9.生成ssh，并添加到github中

        ssh-keygen -t rsa -C "********@163.com" 
        
        cat ~/.ssh/id_rsa.pub 
        
10.安装微信

###### 1)解压缩linux-x64.tar.gz

###### 2) 将微信添加到启动器

```
sudo mv electronic-wechat-linux-x64/ /opt/
sudo ln -s /opt/electronic-wechat-linux-x64/electronic-wechat /uer/bin/wechat
```

3）Alt+F2 打开搜索wechat，最后锁定到任务栏

11.安装网易云音乐

```
sudo dpkg -i netease-cloud-music_1.0.0_amd64_ubuntu16.04.deb
```

如果发生错误，你可以执行下面的指令：

```
sudo apt-get -f install
```

执行之后，你可以继续执行上面的指令

```
sudo dpkg -i netease-cloud-music_1.0.0_amd64_ubuntu16.04.deb
```

12.修改ubuntu的主题

请参考博客：https://blog.csdn.net/u011227356/article/details/80034498

13.修改蓝牙设备的key，实现蓝牙设备在双系统的应用。

tips：楼主在实践中，发现华为的蓝牙鼠标居然有三个MAC地址，所以请大家注意在操作的过程中注意电脑MAC地址和蓝牙设备MAC地址的匹配，从而才能实现蓝牙设备的双系统实现。

具体操作轻参考链接：https://blog.csdn.net/10km/article/details/61201268

14.修改ubuntu启动项：

请参考链接：https://jingyan.baidu.com/article/afd8f4de58959134e386e969.html

15.安装matlab_linux:

参考链接：https://www.cnblogs.com/taoyuyeit/p/8823311.html
