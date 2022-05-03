## 开发环境

下面介绍了Python的安装和使用方法，以及Python常用的四种环境：Jupyter Notebook，Google Colab，VS Code，PyCharm的安装和使用方法，可根据需要跳转阅读。

### Python安装

**1安装Python**

1.在Python官网（https://www.python.org ）点击“Downloads”，在展开页面中选择需要下载的版本。以Windows系统的Python 3.10.1为例，如下图所示进行操作。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image001.png)

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image002.png)

2.如下图所示，双击.exe文件安装，注意勾选“添加到路径”，这样可以将 Python 命令工具所在目录添加到系统 Path 环境变量中，方便以后运行 Python 命令以及开发程序。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image003.png)

3.检查Python是否安装成功

在命令行窗口输入以下命令进入Python专属界面。
```
Python
```
接着输入以下命令。
```py
import this
```
出现下图内容即代表安装成功。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image004.png)

**2 使用Python**

1.安装完成即可在“开始”菜单找到Python。可以通过打开IDLE进行编程，以Python3.9为例，如下图所示。也可以使用之后介绍的其他开发环境。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image005.png)

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image006.png)

2.安装Python库

（1）安装NumPy

Python安装完成后，在命令行窗口输入以下命令，进入Python。
```
Python
```
输入以下命令进行安装及测试。
```
from numpy import *

eye(4)
```
出现如下图内容即安装成功。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image007.png)

（2）安装matplotlib包

在命令行窗口输入以下命令进行安装。
```
pip install matplotlib
```
出现如下图内容即安装成功。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image008.png)

同样地，在命令行窗口输入以下命令进入Python测试。
```
Python
```
输入如下代码：
```
import matplotlib.pyplot as plt

labels='frogs','hogs','dogs','logs'

sizes=15,20,45,10

colors='yellowgreen','gold','lightskyblue','lightcoral'

explode=0,0.1,0,0

plt.pie(sizes,explode=explode,labels=labels,colors=colors,autopct='%1.1f%%',shadow=True,startangle=50)

plt.axis('equal')

plt.show()
```
弹出如下图所示图窗即安装成功。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image009.png)

（3）安装scipy包

在命令行窗口输入以下命令进行安装。
```
pip install scipy
```
测试是否安装成功。在命令行窗口输入以下命令进入Python

输入以下命令：
```
from scipy import constants

# 一英亩等于多少平方米

print(constants.acre)
```
通过导入 scipy 的常量模块 constants 来查看一英亩等于多少平方米，测试安装是否成功。出现如下图内容即为安装成功。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image010.png)

### Jupyter Notebook

**1 介绍**

Jupyter Notebook是基于网页的用于交互计算的应用程序。其可被应用于全过程计算：开发、文档编写、运行代码和展示结果。

Jupyter Notebook以网页的形式打开，可以在网页页面中直接编写代码和运行代码，代码的运行结果也会直接在代码块下显示的程序。如在编程过程中需要编写说明文档，可在同一个页面中直接编写，便于作及时的说明和解释。

**2 安装和使用方法**

1.保证计算机已安装2.x或3.x版本的Python。

2.在命令行窗口使用pip命令安装Jupyter Notebook：

（1）将pip升级到最新版本
```
pip install --upgrade pip #Python 2.x

pip3 install --upgrade pip #Python 3.x
```
在命令行出现```No module named ‘pip’```报错时，通过以下两条命令修复。
```
Python -m ensurepip

Python -m pip install –upgrade pip
```
（2）安装Jupyter Notebook
```
pip install jupyter notebook #Python 2.x

pip3 install jupyter notebook #Python 3.x
```
当出现下图中内容时代表安装成功。
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image011.png)

3.另一种方法是通过安装Anaconda来安装Jupyter Notebook，因为Anaconda可以自动安装Jupter Notebook及其他工具，还有Python中超过180个科学包及其依赖项。

Anaconda在其官方网址https://repo.anaconda.com/archive/ 根据电脑系统和Python版本下载合适版本。其页面如下图所示。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image012.png)

也可以在https://www.anaconda.com/products/individual 直接安装最新的Anaconda，然后用conda create命令来创建虚拟环境即可，不用非得找到对应的Anaconda来装。

例如你要建一个Python3.5的虚拟环境（其中myenv是这个环境的名称，可以自定）：
```
conda create -n myenv Python=3.5
```
然后用以下命令进入该虚拟环境即可：
```
activate myenv
```
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image013.png)

点击“Get Additional Installer”下的图标查找更多版本。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image014.png)

下载完成后启动安装程序。安装过程均选用默认选项即可。

4.运行Jupyter Notebook

在应用程序中找到Jupyter Notebook，单击打开，自动跳转网页，浏览器地址栏中默认地将会显示：http://localhost:8888 。其中，“localhost”指的是本机，“8888”则是默认端口号。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image015.png)

如果设置了密码，会出现以上页面。如果没有设置密码或第一次使用，会直接出现如下主页面。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image016.png)

“Upload”上传本机文件，“New”新建文件。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image017.png)

建立Python文件出现如下页面：

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image018.png)

这就是NoteBook的交互界面，如下图所示，我们可以对文档进行编辑、运行等操作。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image019.png)

更多详细内容参见Jupyter官方文档：https://docs.jupyter.org/en/latest/

### Google Colab

**1 介绍**

Colaboratory 简称“Colab”，是 Google Research 团队开发的一款产品。在 Colab 中，任何人都可以通过浏览器编写和执行任意 Python 代码。它尤其适于实现机器学习、数据分析和教育目的。

从技术上说，Colab 是一种托管式 Jupyter 笔记本服务。用户无需进行设置，就可以直接使用，同时还能获得 GPU 等计算资源的免费使用权限。Jupyter 是一个开放源代码项目，而 Colab 是在 Jupyter 基础之上开发的。通过 Colab，用户无需下载、安装或运行任何软件，就可以使用 Jupyter 笔记本并与他人共享。

简而言之，Colab相当于Jupyter Notebook的在线版本，支持Google Dirve作为云端数据，提供了远端GPU作为运行的主机，类似Jupyter的代码段分块实时运行显示结果。

**2 使用方法**

1.注册Google账号（需要使用外网）；

2.打开Google Chrome搜索Google Colab，点击进入网址，界面如下图所示。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image020.png)

3.本地数据上传基于Google Drive，点击如下图中红框图标进入Drive。

注意：所有线上编辑的代码必须保存在云盘空间内，否则下次打开会丢失。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image021.png)


如图所示，展开“我的云端硬盘”→“Colab Notebooks”中为新建的ipnb代码文件；还可以点击“计算机”上传测试数据和本地代码。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image022.png)

4.使用方法和Jupyter Notebook使用方法一致，分段运行代码段；或者在代码端输入类似命令行语句。
```
Python test.ipnb
```
如下图所示，全部运行当前ipnb文件（必须为当前文件，否则需要更改路径）。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image023.png)

### VS Code

**1 介绍**

VSCode 全称 Visual Studio Code，是微软出的一款轻量级代码编辑器，免费、开源而且功能强大。语法方面：支持几乎所有主流程序语言，并能对语言的语法高亮、只能代码补全、自定义热键、括号匹配、代码片段、代码对比Diff、GIT等特性，支持插件扩展。

**2 安装和使用方法**

1.进入官方网站https://code.visualstudio.com/ ，如下图所示，选择合适的VScode版本下载。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image024.png)

下载完成后启动安装程序。安装过程均选用默认选项即可。

2.安装完成后，按照VScode内部提示，先进行主题、语言的基础设置。

如需进行函数库的安装，可在命令行窗口中使用pip命令完成。格式如下：
```
pip install + 所安装库的名字
```
3.VS code与Python的联合

（1）输入以下命令，查看第三方安装包是否正确。
```
pip list
```
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image025.png)

（2）安装flake8，输入以下命令：
```
pip install flake8
```
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image026.png)

（3）安装yapf，输入以下命令：
```
pip install yapf
```
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image027.png)

（4）配置VS code插件

打开VS code，按下快捷键Ctrl + shift + X进入插件管理页面，搜索Python点击安装。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image028.png)

（5）配置工作区域

如下图所示，点击“设置”（界面左下角）。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image029.png)

在工作区的settings.json中编写如下代码：
```
{

"Python.linting.flake8Enabled": true,

"Python.formatting.provider": "yapf",

"Python.linting.flake8Args": ["--max-line-length=248"],

"Python.linting.pylintEnabled": false

}
```
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image030.png)

（6）如下图所示，编写Python文件验证，点击F5运行。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image031.png)

### PyCharm

**1简介**

PyCharm是一种Python IDE(Integrated Development Environment，集成开发环境)，带有一整套可以帮助用户在使用Python语言开发时提高其效率的工具，比如调试、语法高亮、项目管理、代码跳转、智能提示、自动完成、单元测试、版本控制。此外，该IDE提供了一些高级功能，以用于支持Django框架下的专业Web开发。

**2 安装/使用方法**

1.从网站下载pycharm

（1）点击打开链接http://www.jetbrains.com/pycharm/download/#section=windows ，如下图所示，根据电脑系统选择合适版本，对于Windows系统选择下图中红色圈中的区域。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image032.png)

（2）下载完成后打开文件夹如下图所示：

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image033.png)

（3）直接双击下载好的exe文件进行安装，安装截图如下：

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image034.png)

（4）点击Next进入下一步：

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image035.png)

（5）点击Next进入下一步：

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image036.png)

（6）点击Install进行安装：

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image037.png)

（7）安装完成后出现下图界面，点击Finish结束安装：

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image038.png)

2.pycharm创建程序方法

（1）单击桌面上的pycharm图标进入pycharm，出现如下图所示窗口，选择第二个选项，然后点击Ok。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image039.png)

（2）点击下图中的Accept选项进入下一步。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image040.png)

（3）进入下图页面，点击ok选项。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image041.png)

（4）进入下一步，如下图所示：

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image042.png)

（5）点击Create New Project，进入如下图所示界面，图中的interpreter是选择你安装的Python，Location可以自定义项目存放目录，选择好后，点击create。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image043.png)

（6）如下图所示，在进入的界面，鼠标右击下图中箭头指向的地方，然后最后选择Python file，在弹出的框中填写文件名（任意填写）。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image044.jpg)

（7）文件创建成功后便进入如下的界面，便可以编写自己的程序了，也可以自己设置背景。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83/image045.jpg)
