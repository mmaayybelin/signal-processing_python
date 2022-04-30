# Kivy

## 1介绍和安装方法

Kivy是一个优秀的基于Python的GUI库，可以利用Python快速编程的特点快速编写windows, linux, mac, android, ios等主流平台的应用程序，我们可以用它来将Python程序打包为安卓的apk安装文件。。同wxPython、PyQt相比，最大的优点是可以快速地编写移动应用程序。

### 1.安装Kivy

确保已安装Python后，在命令行窗口依次输入以下三行指令。
```
python -m pip install docutils pygments pypiwin32 kivy.deps.sdl2 kivy.deps.glew

python -m pip install kivy.deps.gstreamer

python -m pip install kivy
```
出现的结果如以下系列图所示。如果过程中提示升级，则按照给出的指令进行升级。
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/kivy/image001.jpg)
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/kivy/image002.jpg)
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/kivy/image003.jpg)
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/kivy/image004.jpg)

再输入以下指令，安装kivy官方示例。
```
python -m pip install kivy_examples
```
如下图所示即为安装成功。
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/kivy/image005.jpg)

### 2.测试是否安装成功
```py
from kivy.app import App

from kivy.uix.button import Button

class TestApp(App):

def build(self):

return Button(text='iPaoMi')

TestApp().run()
```
将以上代码保存为py文件并运行，若出现如下图所示界面，则说明安装成功。
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/kivy/image006.jpg)

## 2 使用方法示例

### 1.创建kivy应用程序的步骤

（1）继承App类；

（2）实现它的build()方法，它能返回一个部件的实例（你的部件树的根部件）；

（3）实例化该类，同时调用它的run()方法。

代码示例如下：
```py
import kivy

#kivy.require('2.0.0') #用你当前的kivy版本替换

from kivy.app import App #导入Kivy应用模块

from kivy.uix.label import Label # 从UIX模块导入标签

#主程序

class MyApp(App): #定义基类MyApp

def build(self): #初始化并返回根部件

return Label(text='Hello world') #初始化一个标签文本“Hello world”并以其作为根部件返回

#实例化MyApp类并运行run()方法，run()方法是应用的入口

if __name__ == '__main__':

MyApp().run()
```
将以上代码保存为py文件并运行。结果如下图：
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/kivy/image007.jpg)

### 2.Kivy的UIX模块

UIX用户界面模块，包含了常用的各种控件（Widgets）和布局（Layouts），可以通过复用来快速构建用户界面。

（1）控件是各种用户界面元素，可以添加到程序中来提供各种功能，如文件浏览器，按钮、滑动页、列表等。

可以通过以下参数设置控件属性：

-   Text：表示文本内容。

-   Font_size：表示字体大小。

-   Size_hint：表示控件的比例，即相对父窗口宽度和高度，传入值必须在0\~1之间，如[0.5,0.4]，小数点前的0可以省略。

-   Pos_hint：表示控件的相对坐标位置。在x轴方向上：‘x’表示左边界，‘center_x’表示垂直中线，‘right’表示右边界；在y轴方向上：‘y’表示下边界，‘center_y’表示水平中线，‘top’表示上边界。必须传入一个字典，如{‘center_x’:0.2,’center_y’:0.5’}。

-   Background_color：表示控件的背景颜色。

之前代码中使用的Label（标签）就是一种控件。类似地， Button（按钮）控件的使用方法如以下代码所示。
```py
from kivy.app import App

from kivy.uix.button import Button#导入Button控件

class KivyButton(App):

def build(self):

return Button(text="Welcome to Kivy!",background_color=(100,0,50,50),

pos=(300,350), size_hint = (.25, .18))#设置文本和控件属性

if __name__ == "__main__":

KivyButton().run()
```
运行结果如下图所示。
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/kivy/image008.jpg)

（2）布局是控件的排列方式，如网格布局、箱式布局等。

可以通过以下参数设置布局属性：

-   padding：表示布局及其子元素之间的填充像素，可由以下三种形式指定：

    1.  四参数列表： [padding_left，padding_top，padding_right，padding_bottom]

        1.  二参数列表： [padding_horizontal，padding_vertical]

            1.  单个参数： padding=10

-   spacing：表示子窗口小部件之间的空间。

-   orientation：表示布局方向水平或垂直。

以常用的BoxLayout（箱式布局）为例，代码如下。
```py
from kivy.app import App

from kivy.uix.button import Button

from kivy.uix.boxlayout import BoxLayout

class boxLayoutExample(App):

def build(self):

layout = BoxLayout(orientation='vertical', spacing=15, padding=10) #创建Layout

buttons = [str(i) for i in range(7)] #设置按键的标签

#循环将按键加入到布局中

for i in range(7):

button = Button(text=buttons[i], size_hint=(.5, .5),

pos_hint={"center_x": .5, "center_y": .5})

layout.add_widget(button)

return layout

if __name__ == "__main__":

boxLayoutExample().run()
```
运行结果如下图所示。
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/kivy/image009.jpg)

### 3.添加事件和回调函数

EventDispatcher（事件分派器）是Kivy框架中最重要的基类之一。通过这个类，用户可以注册各种事件，然后分发给对应的部件。控件类Widget, 动画类Animation 以及时钟类Clock 都属于事件分派器。

根据事件的调用和发生情况，可以分为计划周期事件、计划一次性事件、触发事件、控件事件和自定义事件。

| 事件类型       | 说明                                                                                                                         |
|----------------|------------------------------------------------------------------------------------------------------------------------------|
| 计划周期事件   | 使用schedule_interval()函数，可实现每秒对某个函数或方法进行指定次数的调用。                                                  |
| 计划一次性事件 | 使用schedule_once()函数，可实现对某个函数在指定时间之后调用。                                                                |
| 触发事件       | 只计划在下一帧调用一次，而不允许重复调用。                                                                                   |
| 控件事件       | 包括：1.属性事件，若控件的位置或大小等属性发生改变，会触发一个事件；2.控件定义的事件，例如按钮被按下或者松开会触发一个事件。 |
| 自定义事件     | 要使用自定义事件创建事件分派器，需要首先在类中注册事件名称，然后创建同名的方法。                                             |


这里主要介绍控件事件。要利用一个事件，必须要对其绑定回调。当事件被分派的时候，该特定事件相关的参数将被用于调用回调。通常在py文件使用bind()方法绑定处理函数。

Kivy的控件属性（Property），默认提供了一个on_事件。在属性被改变的时候，就会调用这个事件。以Button控件为例，Button有以下两个事件：

| 事件       | 说明                       |
|------------|----------------------------|
| on_press   | 按下按钮时触发该事件       |
| on_release | 按下按钮并释放时触发该事件 |



代码示例：
```py
from kivy.app import App

from kivy.uix.button import Button

from kivy.uix.boxlayout import BoxLayout

class boxLayoutExample(App):

def build(self):

layout = BoxLayout(orientation='vertical', spacing=15, padding=10)

buttons = [str(i) for i in range(7)]

for i in range(7):

button = Button(text=buttons[i], size_hint=(.5, .5),

pos_hint={"center_x": .5, "center_y": .5})

#将on_press事件绑定到mycallback回调函数上

button.bind(on_press=self.mycallback)

layout.add_widget(button)

return layout

#定义一个回调函数，当属性值改变，即事件被触发时调用回调

def mycallback(self, instance):

print('你按下了{}键'.format(instance.text))#打印相应按钮的文本属性

if __name__ == "__main__":

boxLayoutExample().run()
```
运行结果如下图所示。
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/kivy/image010.jpg)

## 3 APP打包方法

将python文件打包成apk文件,有如下3个方法:

1.通过Buildozer(在linux环境下实现,集成式框架比较容易实现);

2.通过python for android(可以在windows下实现，但需要安装配置许多内容,较为繁琐);

3.通过Kivy Launcher上打包(需要用到谷歌市场)。

详细内容可以参见以下网址：

1.官方打包教程：

[Create a package for Android — Kivy 2.0.0 documentation](https://kivy.org/doc/stable/guide/packaging-android.html)

2.CSDN上通过Buildozer打包的教程：

[通过Kivy将Python文件打包成apk_成功唯有积累，没有奇迹。-CSDN博客_kivy打包apk](https://blog.csdn.net/qq_29027865/article/details/79191775)
