

# 用DOS命令下载三星固件

### 为什么要使用DOS命令下载固件？

- SamFirm和Frija工具已经不可用
- DOS命令下载快速，轻量，稳定
- 从官方服务器下载三星任何固件



### 一、准备工作

- [Python官网下载地址](https://www.python.org/downloads/release/python-395/)
- [get-pip.py官网下载地址](https://bootstrap.pypa.io/get-pip.py)
- [Samloader工具GiHub开源地址](https://github.com/nlscc/samloader)
- 爱折腾的搞机友可以自己官网下载。【[蓝奏云](https://dashan3.lanzoui.com/iy2SApn1ove)】下载解压可获得以上全部

![0](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Firmware_Images/image_0.png)

- [三星驱动下载地址可以参考上一篇教程](https://shimo.im/docs/99GCwYhv8pP6cvqD/)



### 二、python安装及配置

- 用`这里恩恩` 提供的下载地址解压获得以下内容：

![1](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Firmware_Images/image_1.png)

- 解压`python-3.9.5-embed-amd64.zip`到`D:`盘（推荐）
- 如图：

![2](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Firmware_Images/image_2.png)

![3](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Firmware_Images/image_3.png)

![4](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Firmware_Images/image_4.png)

[配置环境变量这里简单说一下，具体详细步骤参考第一篇文章](https://shimo.im/docs/99GCwYhv8pP6cvqD/ ) 



- 系统变量中配置`Python`

![5](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Firmware_Images/image_5.png)

- 系统`Path`变量中配置`Python`变量：

![6](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Firmware_Images/image_6.png)

- 完成**第一步**环境变量配置。



###  三、修改python39.pth文件

![7](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Firmware_Images/image_7.png)



### 四、安装get-pip.py

![8](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Firmware_Images/image_8.png)



- 把文件`get-pip.py`复制到`python-3.9`文件夹根目录中，该地址下运行`cmd`

![9](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Firmware_Images/image_9.png)

```shell
cmd窗口输入

//安装pip 
python get-pip.py
```

![10](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Firmware_Images/image_10.png)



出现如下命令说明安装pip成功，现在`python-3.9`根目录多了两个文件夹，如图：



![11](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Firmware_Images/image_11.png) 3、在配置文件`python39._pth`中用记事本打开加入`Lib\site-packages`如图：

![12](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Firmware_Images/image_12.png)

4、把`Scripts`文件夹配置到`Path`变量中

![13](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Firmware_Images/image_13.png)



环境变量配置完毕 



五、安装`samloader-master`

![14](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Firmware_Images/image_14.png)1、解压

`samloader-master.zip`，解压地址下运行`cmd`

![15](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Firmware_Images/image_15.png) 



- `cmd`窗口输入命令来安装`samloader-master`

```
//安装samloader-master 
python setup.py install

如图：
```

![16](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Firmware_Images/image_16.png)

`到这里环境已经搭建完毕，可以通过任意位置打开cmd用命令来获取任意的三星固件了`





### 六、用DOS命令下载固件获取固件命令：

`注意后面` `.` `不要忽略，命令没有换行符，因为屏幕太窄有些设备看起来命令间有换行`



`检查三星Galaxy设备的最新固件`

```shell
samloader -m <model> -r <region> checkupdate
```

`例如：检查中国 (CHC) 的 Galaxy S21 (SM-G9910) 的最新固件，命令应如下所示：`

```shell
samloader -m SM-G9910 -r CHC checkupdate
```

`该命令应输出固件版本，例如：`

```shell
G9910ZCU2AUDD/G9910CHC2AUDD/G9910ZCU2AUE1/G9910ZCU2AUDD
```

`复制显示的完整固件版本。你将在下一个命令中需要它。`





`使用以下命令为您的三星 Galaxy 设备下载最新的固件更新：`

```shell
samloader -m <model> -r <region> download -v <version> -O <output-dir>
```

`我想在"CHC"区域为 SM-G9910 下载上面输出的最新固件，那么命令应该是：`

```shell
samloader -m SM-G9910 -r CHC download -v G9910ZCU2AUDD/G9910CHC2AUDD/G9910ZCU2AUE1/G9910ZCU2AUDD -O .
```

`下载进度将显示在cmd窗口`

```shell
downloading SM-G9910_1_20210512142736_ofnn115ugq_fac.zip.enc4
[###########                     ] 44281/119835 - 00:07:40
```





`从三星服务器下载的固件更新文件以.enc2格式（对于较旧的设备）或.enc4格式（对于较新的设备）进行解密。因此，你必须将固件文件解密为常规.zip格式。解密下载的 enc2/enc4 固件文件，请使用以下命令：`

```shell
samloader -m <model> -r <region> decrypt -v <version> -V <enc-version> -i <input-file> -o <output-file>
```

`我想在 CHC 区域为我的 Galaxy S21 (SM-G9910) 解密固件文件 (SM-G9910_1_20210512142736_ofnn115ugq_fac.zip.enc4)，命令应该是：`

```shell
samloader -m SM-G9910 -r CHC decrypt -v G9910ZCU2AUDD/G9910CHC2AUDD/G9910ZCU2AUE1/G9910ZCU2AUDD -V 4 -i SM-G9910_1_20210512142736_ofnn115ugq_fac.zip.enc4 -o SM-G9910_1_20210512142736_ofnn115ugq_fac.zip
```



























注意你在什么地方运行的`cmd`窗口，下载的固件就在什么位置。

推荐桌面创建`ROM文件夹`，在`ROM文件夹根目录`运行`cmd`，这样下载的固件就在`ROM`文件夹下

用`Galaxy S21 SM-G9910` 作为演示机型，注意变通



![17](https://github.com/Dashan-37/PP_Tutorial/raw/master/Images/Firmware_Images/image_17.png) 
