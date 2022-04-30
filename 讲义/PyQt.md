# PyQt框架

## 1 PyQt5简介

Qt是由Qt Company开发的跨平台C++图形用户界面应用程序开发框架。PyQt是用于创建GUI应用程序的Python工具包，具有多个版本。

PyQt5 是Digia的一套Qt5与python绑定的应用框架，同时支持2.x 和3.x，Qt库由Riverbank Computing开发， 是最强大的GUI库之一。

PyQt5的官方网站<https://www.riverbankcomputing.com/static/Docs/PyQt5/>。

## 2 PyQt5安装及环境配置

PyQt5的安装方式有两种，一是通过pip安装Pyqt5和PyQt5-tools，二是通过PyCharm为单独项目安装配置。就实际操作和使用推荐PyCharm进行。

**1. pip安装PyQt5**

步骤如下：

1) 运行(Win+R)键，输入cmd打开命令行窗口；

2) 输入命令```pip install pyqt5```，完成PyQt5包安装，出现下图所示内容即为成功。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/pyqt/image001.png)

3) 输入命令```pip install pyqt5-tools```，完成pyqt5-tools包安装，出现下图所示内容即为成功。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/pyqt/image002.png)

**2. PyCharm安装配置PyQt5**

单独项目配置解释器，因为在PyCharm中用户可以为每个新建项目（Project）配置虚拟环境，我们可以根据项目需要配置需要使用到的库，区别于使用本地python解释器。

步骤如下：

1) 新建项目工程，注意选择“New environment using Virtualenv”（虚拟环境），如图。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/pyqt/image003.jpg)

2) 配置虚拟环境，安装PyQt5和pyqt5-tools，点击File-\>settings-\>Project: projectName-\>Python interpreter，界面如图。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/pyqt/image004.png)

进入界面后点击“+”，在搜索框搜索pyqt5和pyqt5-tools，点击“Install Package”，显示安装成功即可，pyqt5-tools配置同理，在默认库的基础上添加PyQt5和pyqt5-tools，具体界面如下。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/pyqt/image005.png)

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/pyqt/image006.png)

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/pyqt/image007.png)

相较于默认环境，增加了PyQt5和pyqt5-tools的相关环境，如图。
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/pyqt/image008.png)

3) 添加External Tools，点击File-\>settings-\>Tools，点击“+”，添加如图 的QT Design和PyUIC程序，方便于直接在项目右键，点击External Tools直接进入配置好的环境中用于GUI编程设计的两个应用程序。QT Design可以在程序内直接拖拽模块进行GUI的设计编程，生存.ui文件；PyUIC用于将.ui文件转化为.py代码文件用以查看或编辑。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/pyqt/image009.png)

QT Designer，在Name输入QT Designer，Program选择目标程序designer.exe，地址为
```
D:\\pyhton_testcode\\pyqtdemo\\venv\\Lib\\site-packages\\qt5_applications\\Qt\\bin\\designer.exe
```
其中pyqtdemo为项目名称，如果找不到可以在当前项目其他文件下找到designer.exe即可，Working directory为.ui文件输出路径，输入```$ProjectFileDir$```，意为输出在当前项目文件下。

PyUIC，在Name输入```PyUIC```，Program选择目标程序pyuic5.exe，地址为```D:\\pyhton_testcode\\pythonProject2qttest\\venv\\Scripts\\pyuic5.exe```，Argument为环境变量参数，输入```$FileName$ -o $FileNameWithoutExtension\$.py```，Working directory为.ui文件输出路径，输入```\$ProjectFileDir\$```。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/pyqt/image010.png)

4) 使用GUI界面编程，在项目右键，选择External Tools，点击需要使用的工具即可进入程序。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/pyqt/image011.png)

## 3 PyQt5主要类

PyQt5类分为很多模块，主要模块有：

| 名称            | 功能                                                                                                                                   |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------|
| QtCore          | 其他模块使用的核心非GUI类。此模块用于处理时间、文件和目录、各种数据类型、流、URL、MIME类型、线程或进程。                               |
| QtGui           | 图形用户界面组件，包含类窗口系统集成、事件处理、二维图形、基本成像、字体和文本。                                                       |
| QtWidgets       | 包含创造经典桌面风格的用户界面提供了一套UI元素的类。                                                                                   |
| QtMultimedia    | 用于低级多媒体编程的类，包含的类来处理多媒体内容和API来访问相机和收音机的功能。                                                        |
| QtBluetooth     | 提供蓝牙API，用于蓝牙设备间的连接。                                                                                                    |
| QtNetwork       | 包含类的扫描设备和连接并与他们互动。描述模块包含了网络编程的类。这些类便于TCP和IP和UDP客户端和服务器的编码，使网络编程更容易和更便携。 |
| QtPositioning   | 包含类的利用各种可能的来源，确定位置，包括卫星、Wi-Fi、或一个文本文件。                                                                |
| Enginio         | 实现了客户端库访问Qt云服务托管的应用程序运行时。                                                                                       |
| QtWebSockets    | 模块包含实现WebSocket协议类。                                                                                                          |
| QtWebKit        | 一个基于Webkit2图书馆Web浏览器实现类。                                                                                                 |
| QtWebKitWidgets | 包含的类的基础webkit1一用于qtwidgets应用Web浏览器的实现。                                                                              |
| QtXml           | 包含与XML文件的类。这个模块为SAX和DOM API提供了实现。                                                                                  |
| QtSvg           | 提供了显示SVG文件内容的类。可伸缩矢量图形（SVG）是一种描述二维图形和图形应用的语言。                                                   |
| QtSql           | 模块提供操作数据库的类。                                                                                                               |
| QtTest          | PyQt5应用程序的单元测试。                                                                                                              |



## 4 PyQt5编程

PyQt5类似Matlab中的app编程有基于代码编程和基于界面模块拖拽编程的两种方式。

**1. 基于代码编程**

可以使用过程式编程如案例1，创建一个对象后对其参数进行实例化；或者面向对象编程如案例2，通过继承Qt中已有的类（class），构造数据（data）和方法（methods）。

> 案例1 创建简单窗口
```py
import sys

from PyQt5.QtWidgets import QApplication, QWidget

def show_w():

'显示窗口'

app = QApplication(sys.argv) # 所有的PyQt5应用必须创建一个应用（Application）对象。

# sys.argv参数是一个来自命令行的参数列表。

w = QWidget() # Qwidget组件是PyQt5中所有用户界面类的基础类。我们给QWidget提供了默认的构造方法。

# 默认构造方法没有父类。没有父类的widget组件将被作为窗口使用。

w.resize(500, 500) # resize()方法调整了widget组件的大小。它现在是500px宽，500px高。

w.move(500, 100) # move()方法移动widget组件到一个位置，这个位置是屏幕上x=500,y=200的坐标。

w.setWindowTitle('Simple') # 设置了窗口的标题。这个标题显示在标题栏中。

w.show() # show()方法在屏幕上显示出widget。一个widget对象在这里第一次被在内存中创建，并且之后在屏幕上显示。

sys.exit(app.exec_()) # 应用进入主循环。在这个地方，事件处理开始执行。主循环用于接收来自窗口触发的事件，

# 并且转发他们到widget应用上处理。如果我们调用exit()方法或主widget组件被销毁，主循环将退出。

# sys.exit()方法确保一个不留垃圾的退出。系统环境将会被通知应用是怎样被结束的。

if __name__ == '__main__':

show_w()
```
程序运行结果：

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/pyqt/image012.png)

> 案例2 创建带图标的窗口

窗口图标通常是显示在窗口的左上角，标题栏的最左边。
```py
import sys

from PyQt5.QtWidgets import (QWidget, QToolTip, QDesktopWidget, QMessageBox,QTextEdit,QLabel,

QPushButton, QApplication,QMainWindow, QAction, qApp, QHBoxLayout, QVBoxLayout,QGridLayout,

QLineEdit)

from PyQt5.QtGui import QFont,QIcon

from PyQt5.QtCore import QCoreApplication

#导入相关模块

# ##***应用图标***## #

class AppIcon(QWidget):

def __init__(self):

super().__init__()

self.initUI()

def initUI(self):

self.setGeometry(300, 300, 300, 220) # 窗口在屏幕上显示，并设置了它的尺寸。resize()和remove()合而为一的方法。

# 前两个参数定位了窗口的x轴和y轴位置。第三个参数是定义窗口的宽度，第四个参数是定义窗口的高度。

self.setWindowTitle('Icon') # 创建一个窗口标题

self.setWindowIcon(QIcon('t1.jpg')) # 创建一个QIcon对象并接收一个我们要显示的图片路径作为参数。

self.show()

if __name__ == '__main__':

app = QApplication(sys.argv)

ex = AppIcon()

sys.exit(app.exec_())
```
程序运行结果：

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/pyqt/image013.png)

**2) 基于界面模块编程**

PyCharm在新建项目中配置好环境后，使用External Tools中QT Designer进行GUI设计，生成test.ui，使用PyUIC将test.ui转换为test.py，在项目中创建main.py导入test.py，创建程序窗口。

(1)界面布局操作

使用External Tools进入QT Designer，选择“Dialog Without Button”创建新文件，从Widget Box拖拽需要组件到界面，组件右键或在属性编辑器设定属性，保存为test.ui。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/pyqt/image014.jpg)

(2)生成Python代码

生成的test.ui右键选择External Tools -\> PyUIC，生成test.py

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/pyqt/image015.png)

生成的test.py并没有程序入口，因此我们在同一个目录下另外创建一个程序叫做“main.py”，并输入如下内容。
```py
import sys

import test

from PyQt5.QtWidgets import QApplication, QMainWindow

if __name__ == '__main__':

app = QApplication(sys.argv)

MainWindow = QMainWindow()

ui = test.Ui_Dialog()

ui.setupUi(MainWindow)

MainWindow.show()

sys.exit(app.exec_())
```
创建程序入口如下图：

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/pyqt/image016.png)

运行main.py，结果如下：

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/pyqt/image017.png)

(3)设定功能

以上部分只是完成了界面布局的操作，进一步需要为组件设定触发功能，PyQt5设计GUI界面涉及到面向对象的编程方法和事件与信号槽的使用。

GUI程序由事件驱动，事件主要由用户触发，但也可能有其他触发方式：例如网络连接、window manager或定时器。当我们调用QApplication的exec_()方法时会使程序进入主循环。主循环会获取并分发事件。

在事件模型中，有三个参与者：事件源，事件对象，事件接收者。

事件源是状态发生变化的对象。它会生成事件。事件(对象)封装了事件源中状态的变动。事件接收者是要通知的对象。事件源对象将事件处理的工作交给事件接收者。

PyQt5有一个独特的signal&slot(信号槽)机制来处理事件。信号槽用于对象间的通信。signal在某一特定事件发生时被触发，slot可以是任何callable对象。当signal触发时会调用与之相连的slot。

详细的GUI设计可以参考以下PyQt5手册进一步学习。

中文手册<http://code.py40.com/pyqt5/>

<https://github.com/maicss/PyQt-Chinese-tutorial>

外文手册<https://zetcode.com/gui/pyqt5/>

官方文档<https://www.riverbankcomputing.com/static/Docs/PyQt5/>
