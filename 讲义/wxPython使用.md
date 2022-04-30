# wxPython

## 1 介绍和安装方法

wxPython是Python语言的一套优秀的GUI图形库。允许Python程序员很方便的创建完整的、功能键全的GUI用户界面。 wxPython是作为优秀的跨平台GUI库wxWidgets的Python封装和Python模块的方式提供给用户的。需要用户自行安装。 安装方法如下：

1.确保电脑已安装pip

在命令行窗口，输入命令```pip```检查pip安装情况及版本。

具体情况参见下图：

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image001.png)

2.安装wxPython

**方法一：**

（1）在wxpython官网地址 <https://wxpython.org/Phoenix/snapshot-builds/>根据电脑系统和Python版本选择适宜的版本，复制名称。

如win10系统+python版本3.10可以选择以下名称：

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image002.png)

Mac系统+python版本3.9可使用：
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image003.png)

（2）在命令行窗口输入形如以下格式的代码。
```
pip install + 网址 + 名称
```
例如：
```
pip install <https://wxpython.org/Phoenix/snapshot-builds/wxPython-4.1.2a1.dev5259+d3bdb143-cp310-cp310-win_amd64.whl>
```
出现如下图所示界面即为安装成功。
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image004.png)

**方法二：**

（1）如方法一，在官网选择适宜版本文件，然后直接下载。

或者在wxPython的PyPI项目页面进行下载，网址为[https://pypi.org/project/wxPython/\#files](https://pypi.org/project/wxPython/#files)。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image005.png)

（2）将下载好的whl文件放在Python安装目录下的scripts文件夹下；

（3）在命令行窗口进入scripts目录下，输入：
```
pip install XX-XXX-XXX.whl

（XX-XXX-XXX.whl是下载的whl文件名）
```
即可安装完毕。

**方法三：**

如需下载安装最新版本，在命令行窗口，输入以下代码即可：
```
pip install -U wxPython
```
检查是否安装成功，可在命令行窗口输入以下代码，即可看到已安装的函数库及其版本：
```
pip list
```
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image006.png)

## 2 使用方法示例

wxPython安装完成后，需要在程序中输入```import wx```来调用该模块。其基本的语法示例如下：
```py
app = wx.App(False)
```
每一个 wxPython 应用程序都是一个 wx.App 实例。对于大多数的简单程序，直接实例化 wx.App 即可。如需创建一个复杂的应用程序，则可对 wx.App class 进行一些扩展。“False” 参数意味着“不要把 stdout 和 stderr 信息重定向到窗口”，也可以不加 “False” 参数。
```py
frame = wx.Frame(None, wx.ID_ANY, “Hello, World!”)
```
完整的语法是x.Frame(Parent, Id, Title)。在本例中，我们使用 “None” 来表示这个frame是顶层的框架，没有父框架；使用 “wx.ID_ANY” 让 wxWidgets 来给我们挑选一个ID。
```py
frame.Show(True)
```
显示这个Frame。
```py
app.MainLoop()
```
表示运行这个应用程序。

整体代码如下：
```py
import wx

app = wx.App(False)

frame = wx.Frame(None, wx.ID_ANY, "Hello, World!")

frame.Show(True)

app.MainLoop()
```
建立并运行一个简单程序，可出现如下图所示的窗口。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image007.png)

wxPython的功能十分强大，可以实现多种功能，比如布局管理、控件、对话框、菜单、工具栏、拖拽、事件等。这里以部分功能为例，说明代码的书写方法。

（1）在布局管理中，如BoxSizer，该定位按行或者列来排列多个控件，同时也允许 Sizer 的嵌套，这时可以构造出非常复杂的布局。
```py
box = wx.BoxSizer(integer orient)
```
（2）在控件中，如Button，该控件仅包含一个文本字符串，用来触发某个动作。如下图：

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image008.png)

（3）可以建立对话框，如MessageDialog，该对话框显示单行或多行消息，并带有 OK、Cancel、Yes 和 No 按钮的选择。在 Windows 下，可以显示可选图标，例如感叹号或问号。
```py
dlg = wx.MessageDialog(None, '消息对话框内容', '标题信息', wx.OK)

dlg.ShowModal()

dlg.Destroy()
```
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image009.png)

（4）建立面板、创建菜单栏。

首先我们生成一个wx.Frame 的子类，并重写它的__init_\_ 方法。
```py
def __init__(self, *args, \*\*kw):

super(demo, self).__init__(*args, \*\*kw)
```
再在框架中创建一个面板，放置一段静态文字：
```
pnl = wx.Panel(self)

st = wx.StaticText(pnl, label="这是面板")

font = st.GetFont()

font.PointSize += 10

font = font.Bold()

st.SetFont(font)
```
创建菜单栏,创建 "关于" 项目的 "帮助" 菜单：
```
self.make_menu_bar()

help_menu = wx.Menu()

about_item = help_menu.Append(wx.ID_ABOUT)

#制作菜单栏，向其中添加两个菜单:

menu_bar = wx.MenuBar()

menu_bar.Append(file_menu, "&文件")

menu_bar.Append(help_menu, "&帮助")

self.SetMenuBar(menu_bar)

#将菜单项的处理函数与 EVT_MENU 事件关联

self.Bind(wx.EVT_MENU, self.on_about, about_item)

#再写下处理函数：

def on_about(self, event):

wx.MessageBox("这是一个小程序", "小程序的帮助", wx.OK | wx.ICON_INFORMATION)
```
将上述代码整理到基本的代码程序中，于是可以得到如下图所示的程序框体：

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image010.png)

如下图，点击帮助里面的关于，会显示出处理函数中的内容：

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image011.png)
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image012.png)

## 3 wxPython控件

**1.关于控件编程的一般思路**

（狭义的）控件(control) 本质上是一种特殊的窗口，在交互中完成特定的功能，如果我们把一般的窗口比作一面墙，那么控件就相当于墙上的挂钟、开关和其他装饰——这说明控件很多时候是依赖某个窗口而存在的。在现实中，若想了解一个人，姓名、性别、工作单位、家庭住址等基本信息是逃不开的要素。控件编程的思路类似，类型、父窗口、位置、大小、ID是控件不可或缺的属性。类型用来区分不同种类的控件，比如按钮、组合框、输入框、列表、进度条、属性页、树视图、状态栏；父窗口(parent window)则表明控件放在哪个窗口上；位置(position)往往是一个坐标，标记控件放在父窗口上的哪个位置；大小(size)往往也是一个坐标，表示控件在横、纵两个方向上要占用多少个尺寸单元；ID则主要用在消息循环中，既可以当作空间的索引，也用以区分某个消息来自哪个控件。

以下列举了各个控件的构造函数和参数等详细信息以供读者查阅。

**2.按钮(button)**

按钮在不同的平台上有不同的样式：

|     ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image013.png)  |    ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image014.png)  |   ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image015.png)      |
|-------------|----------|---------|
| Windows平台 | unix平台 | Mac平台 |


按钮的构造函数如下：

Button(parent, id, label, pos, size, style, validator, name)

除了上一节描述的四个参数以外，其他各个参数含义如下

-   label: 字符串，按钮上的文字；

-   style: 窗口的样式，为以下几个值之一

    -   wx.BU_LEFT: 按钮上的文字或图片左对齐。

    -   wx.BU_TOP: 按钮上的文字或图片上对齐。

    -   wx.BU_RIGHT: 按钮上的文字或图片右对齐。

    -   wx.BU_BOTTOM: 按钮上的文字或图片下对齐。

    -   wx.BU_EXACTFIT: 让按钮的大小恰好适合其中的文字或图片。

    -   wx.BU_NOTEXT: 不显示按钮上的文字，即使已经指定。

    -   wx.BORDER_NONE: 按钮无边框。

按钮控件包含的主要方法如下：

-   GetLabel()：返回按钮上的文字。

-   SetLabel(string)：设置按钮上的文字。

按钮控件只触发一个事件：

-   EVT_BUTTON: CommandEvent类型，当按钮被按下以后触发.

**3.输入框(text control)**

输入框在不同的平台上有不同的样式：

|     ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image016.png)        |  ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image017.png)  |    ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image018.png)  |
|-------------|----------|---------|
| Windows平台 | unix平台 | Mac平台 |


输入框的构造函数如下：

TextCtrl(parent, id, value, pos, size, style, validator, name)

其中value参数是一个字符串，表示输入框中的初始文字。style参数是以下几个之一或组合：

-   wx.TE_PROCESS_ENTER: 按下回车键时触发wxEVT_TEXT_ENTER消息。

-   wx.TE_PROCESS_TAB: 按下TAB键的时候输入TAB字符而不是让焦点转移到其他控件上。

-   wx.TE_MULTILINE: 允许多行输入。

-   wx.TE_PASSWORD: （输密码的时候用）让输入的字符都显示为星号。

-   wx.TE_READONLY: 不允许修改框中的字符串（但可以选择和复制）。

-   wx.TE_AUTO_URL: 自动检测网址并高亮显示，当鼠标点击该网址时触发TextUrlEvents事件。

-   wx.TE_NOHIDESEL: 当控件失去焦点时，已选择的字符保持选择状态。

-   wx.HSCROLL/wx.TE_DONTWRAP: 字符串过长时不自动换行而显示水平滚动条。

-   wx.TE_NO_VSCROLL: 不显示垂直滚动条。

-   wx.TE_LEFT: 左对齐字符串（默认）。

-   wx.TE_CENTRE: 字符串居中。

-   wx.TE_RIGHT: 右对齐字符串。

-   wx.TE_CHARWRAP: （仅适用于多行输入）当字符串足够长以至于一行放不下时，将超出边界的字符换到下一行。

-   wx.TE_WORDWRAP: （仅适用于多行输入）当字符串足够长时以至于一行放不下时，将超出边界的单词换到下一行。

-   wx.TE_BESTWRAP: （默认）根据实际情况在以上两种换行方案中自动选择。

-   wx.TE_CAPITALIZE: 首字母自动大写。

输入框主要包含这些方法：

-   DiscardEdits: 如果内容已保存，则取消“已修改”的标志。

-   GetLineLength(lineNO): 获取某一行的长度。

-   GetLineText(lineNO): 获取某一行的内容。

-   GetNumberOfLines(): 获取行数。

-   IsModified(): 返回“已修改”的标志。

-   IsMultiLine(): 多行返回true，单行返回false。

-   LoadFile(filename): 加载一个文件并显示其文件名。

-   MarkDirty(): 设置“已修改”的标志。

-   SaveFile(filename): 将内容保存至文件中。

输入框可能产生下面这些消息：

-   EVT_TEXT: 当内容发生变化时触发。但调用ChangeValue函数不会触发此消息。

-   EVT_TEXT_ENTER: 当键入回车时触发。

-   EVT_TEXT_URL: 点击识别出的网址后触发。

-   EVT_TEXT_MAXLEN: 当内容的长度达到最大值时触发。

**4.组合框(combobox)**

组合框在不同的平台上有不同的样式：

|      ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image019.png)       |     ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image020.png)     |   ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image021.png) |
|-------------|----------|---------|
| Windows平台 | unix平台 | Mac平台 |


组合框的构造函数如下：

ComboBox(parent, id, value, pos, size, choices, style, validator, name)

除了经典的四个参数以外，其他参数含义如下：

-   value: 字符串，初始选中项的文字。

-   choices: 字符串列表，每一项的文字。

-   style: 组合框的样式，为以下几个值之一。

    -   wx.CB_SIMPLE: 组合框的候选列表一直保持显示在已选项的正下方。

    -   wx.CB_DROPDOWN: 组合框的候选列表以下拉的形式出现，下拉列表会自动收起。

|     ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image022.png)      |      ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image023.png)       |
|-----------|-------------|
| CB_SIMPLE | CB_DROPDOWN |


-   wx.CB_READONLY: 选择的项目不能手动输入，只能从候选列表中挑选。

    -   wx.CB_SORT: 将候选项目按字母序排列。

    -   wx.TE_PROCESS_ENTER: 输入回车键时调用回调函数。

5.列表(list control)

列表是一个非常复杂的控件，列表框在不同的平台上样式如下：

|        ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image024.png)     |      ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image025.png)    |    ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image026.png)     |
|-------------|----------|---------|
| Windows平台 | unix平台 | Mac平台 |


列表的构造函数如下：
```
ListCtrl(parent, id, pos, size, style, validator, name)
```
列表控件可存储的信息量很大，结构也较为复杂，以至于在构造函数中不能指定其内容，而style参数是以下几个之一：

-   wx.LC_LIST: 表头的水平长度根据内容自动调整。

-   wx.LC_REPORT: 像Excel那样的报表，但不一定需要表头。

-   wx.LC_ICON: 大图标，文字可选。

-   wx.LC_SMALL_ICON: 小图标，文字可选。

-   wx.LC_ALIGN_TOP: 图标上对齐。

-   wx.LC_ALIGN_LEFT: 图标左对齐。

-   wx.LC_AUTOARRANGE: 图标自动对齐。

-   wx.LC_EDIT_LABELS: 表项可以编辑。

-   wx.LC_NO_HEADER: 取消表头。

-   wx.LC_SINGLE_SEL: 只允许选择一项。

-   wx.LC_SORT_ASCENDING: 自动升序排列，其中排序的回调函数在wx.ListCtrl.SortItems中指定。

-   wx.LC_SORT_DESCENDING: 自动降序排列。

列表的内容全由其方法指定，主要的方法列举如下：

-   Append(entry): 将一个条目添加至最后一行，参数entry是列表类型，指明每一列应添加什么内容。

-   AppendColumn(heading, format, width): 在最右侧添加一列（仅适用于LVS_REPORT），heading是字符串，为该列的表头；format表示该行文字的对齐方式，默认左对齐；width为列宽，默认-1为自动设置。

-   AssignImageList(ImageList): 让一个图片列表控件(image list control)与该列表控件绑定。

-   ClearAll(): 删除所有内容，包括表头，并触发wxEVT_LIST_DELETE_ALL_ITEMS事件。

-   DeleteAllColumns(): 删除所有表头。

-   DeleteAllItems(): 删除所有项目，但不删除表头。

-   DeleteColumn(col): 删除第col列及所有内容。

-   DeleteItem(item): 删除第item行的内容。

-   EnableAlternateRowColours(true/false): 允许/不允许隔行染色。

-   EnsureVisible(): 把视线拉到第item行上（针对行数太多出现滚动条的情况）。

-   FindItem(start, str, partial): 凭字符串str，从第start行开始寻找某一项，如果partial为true，那么只要某一项中的部分字符与str相同就算找到，为false则需要全字匹配。

-   Focus(idx): 将焦点集中在第idx行上。

-   GetAlternateRowColour(): 获取隔行染的颜色，返回值为wx.Colour类型。

-   GetColumn(col, item): 返回第col列的wx.ListItem对象。

-   GetColumnCount(): 获取列数。

-   GetColumnWidth(col): 获取某一列的列宽（仅限LVS_REPORT）。

-   GetFocusedItem(): 获取焦点所在的那一项，返回wx.ListItem对象。

-   GetImageList(): 获取列表对象绑定的ImageList对象。

-   GetItem(idx): 返回第idx项的wx.ListItem对象。

-   GetItemCount(): 获取项数。

-   GetItemData(): 获取与某一项绑定的数据，该数据是自己设定的。

-   GetItemText(): 获取某一项的文字。

-   GetSelectedItemCount(): 获取被选中的项数。

-   InsertColumn(col, heading, format, width): （仅限LVS_REPORT）在某一列左边插入一列，参数详见AppendColumn。

-   InsertItem(index, label): 在第index行之上插入一行，文字是label。

-   IsEmpty(): 列表为空返回true。

-   IsSelected(idx): 若第idx项被选中就返回true。

-   Select(idx,on): on为true时选择第idx项，否则为反选择。

-   SetColumn(col, item): item为wx.ListItem类型，用其设置第col列。

-   SetColumnWidth(col, width): 设置第col列的宽度。

-   SetItem(info): 设置某一项，info是wx.ListItem类型。

-   SetItemData(data): 设置与某一项关联的数据，data是long类型。

-   SetItemText(idx,text): 设置某一项的数据。

6.单选框(radiobox)

|      ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image027.png)       |    ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image028.png)      |     ![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image029.png)    |
|-------------|----------|---------|
| Windows平台 | unix平台 | Mac平台 |


单选框的构造函数为：
```
RadioBox(parent, id, label, pos, size, choices, validator, name)
```
其中choices为string数组，为各个选项的文字，label是围绕选项的框上的文字。

该控件的主要方法有以下几种：

-   EnableItem(n, true/false): 让第n项（所有计数都从0开始）可以/不可被选择。

-   GetCount(): 获取项数。

-   GetItemLabel(n): 获取第n个选择按钮的文字。

-   GetSelection(): 返回被选中的选项序号。

-   IsItemEnabled(n): 获取第n个选项是否可以/不可被选中。

-   SetItemLabel(n, text): 设置第n个选项的文字为text。

-   SetSelection(n): 让第n个选项被选中。

该控件可能触发的事件仅有EVT_RADIOBOX，在某个选项被选择时触发。

**7.状态栏(status bar)**

状态栏是窗口底部的长条状显示信息的地方，在各种应用程序中非常常见。
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image030.png)

wxPython中状态栏的构造函数如下

StatusBar(parent, id, style, name)

其中style参数为以下几个值之一：

-   wx.STB_SIZEGRIP: 在右下角放置一个可以拖动以改变窗口大小的“把柄”。

-   wx.STB_ELLIPSIZE_START: 当文字过长时，只显示最后一段，同时在左侧让文字淡出。

-   wx.STB_ELLIPSIZE_MIDDLE: 当文字过长时，只显示最前和最后一段，同时在中间让文字淡出。

-   wx.STB_ELLIPSIZE_END: 当文字过长时，只显示最前一段，同时在右侧让文字淡出。

状态栏对象有以下这些方法：

-   GetField(n): 返回状态栏的第n栏，为wx.StatueBarPane对象。

-   GetFieldRect(n): 返回状态栏第n栏的尺寸，为wx.Rect对象。

-   GetFieldsCount(n): 获取状态栏的栏数。

-   GetStatusStyle(n): 获取状态栏第n栏的样式。

-   GetStatusText(n): 获取第n栏的文字。

-   GetStatusWidth(n): 获取第n栏的宽度。

-   SetFieldsCount(n): 将整个状态栏分为n栏。

-   SetStatusText(n): 设置第n栏的文字。

-   SetStatusWidths(n): n是一个数组，元素的个数等于栏数，设置每一栏的宽度。

**8.菜单(menu)和菜单栏(menu bar)**

菜单就像下图这样，是一个个长方形的按钮并在一起得到。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/wxpython/image031.png)

欲创建一个菜单，使用wx.Menu()函数，不需要参数即可返回一个菜单对象，在欲往菜单里添加项目，则需要使用wx.Append方法：
```
Append (id, item, helpString)
```
其中item为字符串，为菜单项的文字，helpString为帮助字符串，当将鼠标放到该项上时，会显示在状态栏上。在item字符串中加入’\\t’字符，后面的字符串则表示快捷键，例如上图中Hello那一项对应的item字符串为

Hello...\\tCtrl-H

若想添加如图中那条灰色的线，调用AppendSeparator()方法即可。

窗口上部的那一条称为菜单栏，可用wx.MenuBar()函数创建，返回wx.MenuBar对象，当创建好菜单和菜单栏之后，可调用菜单栏的Append函数菜单添加到菜单栏中：

Append(menu, text)

menu是创建好的菜单，text则是该菜单的名字，如上图的’File’和‘Help’。创建好菜单之后，调用窗口类的SetMenuBar方法将菜单栏设为本窗口的菜单栏。
