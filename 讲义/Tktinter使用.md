# Tktinter

Python自带了tkinter 模块，安装Python后无需搭建其他环境，直接导入即可使用。它的特点是简单、轻量，满足简单的GUI设计需求，例如制作登录，计算器等界面等。缺点是不够美观，代码较为繁琐。

其图像化编程的基本流程通常包括：

## 一、导入 tkinter模块
```py
import tkinter as tk
```
## 二、创建主窗口
```py
# 调用Tk()方法创建主窗口

root_window =tk.Tk()

# 为主窗口命名

root_window.title('主窗口')

#开启主循环，让窗口处于显示状态

root_window.mainloop()
```
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/tktinter/image001.png)


## 三、添加控件并编写相应的响应函数

**1 添加控件**

1. tktinter中常用控件

| 控件         | 功能                                                        |
|--------------|-------------------------------------------------------------|
| Button       | 按钮控件                                                    |
| Canvas       | 画布控件，用于显示图形元素，如线条或文本                    |
| Checkbutton  | 多选框控件                                                  |
| Entry        | 输入控件，用于显示和接收简单的文本内容                      |
| Frame        | 框架控件,在屏幕上显示一个矩形区域，多用于作为其他控件的容器 |
| Label        | 标签控件,可以显示简单文本和图片                             |
| tkMessageBox | 用于显示你应用程序的消息框。                                |


2. tktinter中控件常见属性

| 属性      | 描述         |
|-----------|--------------|
| Dimension | 大小         |
| Color     | 颜色         |
| Font      | 字体         |
| Anchor    | 锚点（定位） |
| Relief    | 样式         |
| Bitmap    | 位图         |
| Cursor    | 光标         |


3. tktinter中控件常见布局

| 方法    | 描述           |
|---------|----------------|
| pack()  | 简单布局       |
| grid()  | 二维表格式布局 |
| place() | 指定坐标布局   |


4. 示例
```py
import tkinter as tk

# 调用Tk()方法创建主窗口

root_window =tk.Tk()

# 为主窗口命名

root_window.title('主窗口')

# 设置窗口大小:宽x高,

root_window.geometry('450x300')

# 改变背景颜色

root_window.config(background='lightskyblue')

# 设置窗口的透明度

root_window.attributes('-alpha',1)

#更改左上角窗口的的icon图标，加载北京理工大学logo标

root_window.iconbitmap('./bit.ico')

#添加文本内容,并对字体添加相应的格式 font(字体,字号,"字体类型")

text=tk.Label(root_window,text="Hello World!",bg="orange",fg="cyan",font=('Times', 20, 'bold'))

#将上述控件放置在主窗口上方

text.pack(side="top")

# 添加按钮，并设置按钮的文本，利用command参数，实现按下按钮关闭窗口的功能

button=tk.Button(root_window,text="关闭",command=root_window.quit)

# 将上述按钮放置在主窗口下方

button.pack(side="bottom")

#开启主循环

root_window.mainloop()
```
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/tktinter/image002.png)

**2 编写响应（回调）函数**

将要实现的功能封装成函数，传入控件的command参数中即可实现按件的交互功能。
```py
import tkinter as tk

# 调用Tk()方法创建主窗口

root_window =tk.Tk()

# 为主窗口命名

root_window.title('主窗口')

# 设置窗口大小:宽x高,

root_window.geometry('450x300')

# 改变背景颜色

root_window.config(background='lightskyblue')

# 设置窗口的透明度

root_window.attributes('-alpha',1)

#更改左上角窗口的的icon图标，加载北京理工大学logo标

root_window.iconbitmap('./bit.ico')

cnt = 0

s1 = ""

s2 = ""

# 定义回调函数

def callback():

global cnt

cnt = cnt + 1

s1 = "执行回调函数,"

s2 = "第%d次点击"%(cnt)

print(s1 + s2)

text.config(text=s1+s2)

# 点击执行按钮

button = tk.Button(root_window, text="点我", command=callback)

text=tk.Label(root_window,text=s1+s2,bg="orange",fg="cyan",font=('Times', 20, 'bold'))

button.pack()

text.pack()

root_window.mainloop()
```
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/tktinter/image003.png)

## 四、在主事件循环中等待用户触发事件响应。

在程序最后不要忘记调用主窗口mainloop方法即可。
