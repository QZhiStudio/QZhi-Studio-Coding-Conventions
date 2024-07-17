# QZhi Studio 产品编码约定

为了统一 QZhi Studio 成员以及 QZhi Studio 合作开发人员在同一产品中的设计和代码风格，制订此约定。本约定仅作推荐性要求。

## 目录

- [QZhi Studio 产品编码约定](#qzhi-studio-产品编码约定)
  - [目录](#目录)
  - [定义](#定义)
  - [日期约定](#日期约定)
  - [时间约定](#时间约定)
  - [版本约定](#版本约定)
  - [使用开源协议](#使用开源协议)
  - [使用第三方模块和 NOTICE 文件](#使用第三方模块和-notice-文件)
    - [项目使用第三方模块的要求](#项目使用第三方模块的要求)
    - [项目使用 NOTICE 文件的要求](#项目使用-notice-文件的要求)
    - [QZhi Studio 的 NOTICE 文件格式（根据 https://cloud.huawei.com/staticpage/opensource/files\_v2.html 改写）](#qzhi-studio-的-notice-文件格式根据-httpscloudhuaweicomstaticpageopensourcefiles_v2html-改写)
  - [产品文件夹结构约定](#产品文件夹结构约定)
    - [一般性约定](#一般性约定)
    - [单项目产品的项目文件夹命名](#单项目产品的项目文件夹命名)
    - [多项目产品的项目文件夹命名](#多项目产品的项目文件夹命名)
    - [常用的文件夹命名](#常用的文件夹命名)
  - [ReadMe 约定](#readme-约定)
    - [使用 ReadMe 文件的要求](#使用-readme-文件的要求)
    - [ReadMe 文件的一般格式](#readme-文件的一般格式)
  - [Commit message 约定（根据 https://ruanyifeng.com/blog/2016/01/commit\_message\_change\_log.html 和 https://blog.csdn.net/hzf0701/article/details/134367234 整理改写）](#commit-message-约定根据-httpsruanyifengcomblog201601commit_message_change_loghtml-和-httpsblogcsdnnethzf0701articledetails134367234-整理改写)
    - [简明的 Commit message](#简明的-commit-message)
      - [type](#type)
      - [subject](#subject)
    - [完备的 Commit message](#完备的-commit-message)
    - [撤销改动的 Commit message](#撤销改动的-commit-message)
  - [UpdateLog 约定（根据 https://blog.csdn.net/mingtianqingtian/article/details/109771784 整理改写）](#updatelog-约定根据-httpsblogcsdnnetmingtianqingtianarticledetails109771784-整理改写)
    - [一般性要求](#一般性要求)
    - [type](#type-1)
  - [代码风格约定（根据 https://zhuanlan.zhihu.com/p/134433380 整理改写）](#代码风格约定根据-httpszhuanlanzhihucomp134433380-整理改写)
    - [一般排版约定](#一般排版约定)
    - [命名约定](#命名约定)
    - [注释约定](#注释约定)

## 定义

源文件
: 存放代码的文本文件

可执行文件
: 存放二进制代码，可以**直接**在特定平台下执行，实现某个（些）功能的文件

库
: 存放二进制代码，不可以直接执行的文件

项目
: 为了实现某一功能而编写的软件，包括源代码和可执行文件（或库）

项目组
: 多个项目的集合

产品
: 一个项目或一个项目组

## 日期约定

请按照 `yyyy-mm-dd` 的格式

## 时间约定

请按照 `hh:mm` 的格式，二十四小时制

## 版本约定

产品版本格式为 `主版本号.次版本号.修订号[-先行版本信息][+版本编译信息]`

具体版本号制定请参照 https://semver.org/lang/zh-CN/

先行版本信息需要以软件开发的各时期来填写。

Alpha 期（内部测试期）
: 软件起始阶段，极不稳定，不需要写 Commit message 和 Update log，不公开发布

Beta 期（公开测试期）
: 软件主要功能已完善，公开测试，需要写 Commit message 和 Update log，可以增加新功能

RC 期（预发行期）
: 软件已实现规划的所有功能，公开测试，需要写 Commit message 和 Update log，不可以增加新功能

Release 期
: 最终发布版本

## 使用开源协议

为了践行开源精神，一般情况下，请选择 Apache 2.0 开源协议。

要求：

* 在项目根目录放置 LICENSE 文件（这一步可以在 Github 创建项目时完成）
* 在程序所有需要保护的、非第三方模块的源文件起始处，**以注释的形式**写上如下声明
    ```
    Copyright [yyyy] [name of copyright owner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
    ```
    其中，将 `[yyyy]` 替换成代码更新的年份，将 `[name of copyright owner]` 替换为 `QZhi Studio`

## 使用第三方模块和 NOTICE 文件

### 项目使用第三方模块的要求

* 检查第三方模块的**开源协议**或**最终用户协议**是否与当前项目的开源协议和实际相冲突。如果第三方模块的开源协议是（或包含）**GPL及其变种**，请不要使用该模块；如果第三方模块有特殊要求（如 Visual Studio Image Library 只有在使用 Visual Studio 开发的项目中使用），请尽量满足，如果满足不了，请不要使用该模块。
* 布局项目文件夹，存放第三方模块
* 创建或更新 NOTICE 文件

### 项目使用 NOTICE 文件的要求

* 在项目根目录存放 NOTICE 文件

### QZhi Studio 的 NOTICE 文件格式（根据 https://cloud.huawei.com/staticpage/opensource/files_v2.html 改写）

* 项目名称及合法权利声明
    ```
    [name of software]
    Copyright [yyyy] [name of copyright owner]
    ```
    其中，将 `[name of software]` 替换为含 `QZhi` 的项目全名，将 `[yyyy]` 替换成代码更新的年份，将 `[name of copyright owner]` 替换为 `QZhi Studio`
* 空行一次
* `OPEN SOURCE SOFTWARE NOTICE`
* 空行三次
* 声明
    ```
    Please note we provide an open source software notice along with this product. The open source software licenses are granted by the respective right holders. And the open source licenses prevail all other license information with regard to the respective open source software contained in the product, including but not limited to End User Software Licensing Agreement. This notice is provided on behalf of QZhi Studio which may have provided this product to you in your local country.
    ```
* 空行三次
* 免责声明
    ```
    Warranty Disclaimer

    The open source software in this product is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY, without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the applicable licenses for more details.
    ```
* 空行三次
* `Copyright Notice and License Texts`
* 空行三次
* 各模块及其开源协议声明
    ```
    Software: [name of software]

    Copyright notice:

    License: [name of license]

    [license]
    ```
    其中，将 `[name of software]` 替换为含 `模块所有者` 的项目全名，将 `[name of license]` 替换成模块的开源协议全名，将 `[license]` 替换为开源协议文本（如果有重复的开源协议，将除首次出现的该协议文本替换为 `Please see above.`）。
    该部分可以反复出现。每出现一次（除最后一次），在出现部分后空行三次。

## 产品文件夹结构约定

### 一般性约定

* 为每个产品单独新建一个文件夹，即产品根目录
* 若产品只包含一个项目（单项目产品），则产品根目录即为项目根目录
* 若产品为项目组（多项目产品），则产品根目录即为项目组根目录，项目组所包含的项目各应在产品根目录下新建一个与项目同名的文件夹，所新建的文件夹即为项目根目录
* 相对于项目根目录的一级目录一般使用缩写
* 一般情况下，文件夹应使用英文复数形式
* 若文件夹名有多个单词组成，则使用一律小写的方法（如 `usercontrols`）或下划线法（如 `user_controls`）

### 单项目产品的项目文件夹命名

src
: 源码文件夹，相对于项目根目录的一级目录，用于存放源码

bin
: 二进制文件夹，相对于项目根目录的一级目录，用于存放可执行文件或库

res
: 资源文件夹，相对于项目根目录的一级目录，用于存放各种资源

docs
: 文档文件夹，相对于项目根目录的一级目录，用于存放产品文档

logs
: 日志文件夹，相对于项目根目录的一级目录，用于存放日志文件

utils
: 工具文件夹，相对于项目根目录的一级目录，用于存放工具

### 多项目产品的项目文件夹命名

src
: 源码文件夹，相对于**项目**根目录的一级目录，用于存放源码

bin
: 二进制文件夹，相对于**项目组**根目录的一级目录，用于存放可执行文件或库

res
: 资源文件夹，相对于**项目**根目录的一级目录，用于存放各种资源

docs
: 文档文件夹，相对于**项目组**根目录的一级目录，用于存放产品文档

common
: 公用文件夹，相对于**项目组**根目录的一级目录，用于存放反复使用的源代码、资源和库

logs
: 日志文件夹，相对于**项目组**根目录的一级目录，用于存放日志文件

utils
: 工具文件夹，相对于**项目组**根目录的一级目录，用于存放工具

### 常用的文件夹命名

classes
: 类文件

forms
: 窗体文件

modules
: 模块文件

usercontrols
: 用户控件

headers
: 头文件

images
: 图像文件

videos
: 视频文件

rcscripts
: 资源脚本文件

## ReadMe 约定

### 使用 ReadMe 文件的要求

* 文件名为 `README.md`
* 一般放置在产品根目录，若有特殊需要，可将不同的 ReadMe 文件置于不同的文件夹中

### ReadMe 文件的一般格式

* 产品名称
    ```markdown
    # 产品名称
    ```
* 构建工具
    ```markdown
    ## 构建工具

    ...
    ```
* 产品简介
    ```markdown
    ## 产品简介
    
    简要介绍产品功能和优势

    ```
* 安装步骤
    ```markdown
    ## 安装步骤

    ...
    ```
* 使用方法
    ```markdown
    ## 使用方法

    ...
    ```
* 目录结构
    ```markdown
    ## 目录结构

    ...
    ```
    例：
    ```markdown
    ## 目录结构

    ├─bin
    ├─docs
    ├─res
    │  ├─cursors
    │  │  └─gif
    │  ├─htmlpages
    │  ├─icons
    │  ├─img
    │  │  ├─appMode
    │  │  ├─colorsRectangle
    │  │  ├─exCaption
    │  │  ├─scrollbar
    │  │  ├─tlbBrowse
    │  │  ├─tlbFormat
    │  │  ├─tlbMain
    │  │  │  ├─tlbControl
    │  │  │  └─tlbEdit
    │  │  ├─tlbMsg
    │  │  ├─treStruct
    │  │  └─widgets
    │  │      ├─common
    │  │      ├─controls
    │  │      └─regular
    │  └─rc
    ├─src
    │  ├─classes
    │  ├─forms
    │  ├─modules
    │  └─userControls
    └─tools
        └─DrawColorsRectangle
            ├─bin
            └─src
                ├─forms
                └─modules
    ```
    可以使用 Windows 下的 `tree` 命令来生成目录结构，若有需要，还应写上注释

## Commit message 约定（根据 https://ruanyifeng.com/blog/2016/01/commit_message_change_log.html 和 https://blog.csdn.net/hzf0701/article/details/134367234 整理改写）

### 简明的 Commit message

简明的 Commit message 为 `type` + `subject`

在 Alpha 阶段，不要求写 Commit message

#### type

feat
: 新功能（feature）

fix
: 完整的修复 bug

to
: 在一定条件下修复 bug

docs
: 文档（documentation）

style
: 格式（不影响代码运行的变动，即代码风格更改）

refactor
: 重构（即不是新增功能，也不是修改bug的代码变动）

perf
: 代码优化

test
: 增加测试

chore
: 构建过程或辅助工具的变动

merge
: 代码合并

sync
: 同步主线或分支的Bug

#### subject

一般以英语写，要求

* 以动词开头，使用一般现在时，使用第一人称
* 第一个字母小写
* 结尾不加点号（.）

### 完备的 Commit message

在简明的 Commit message 的基础上，添加详细说明（英文）

### 撤销改动的 Commit message

格式：

```
revert: [commit message header]

This reverts commit [SHA].
```

## UpdateLog 约定（根据 https://blog.csdn.net/mingtianqingtian/article/details/109771784 整理改写）

### 一般性要求

* 文件名为 `CHANGELOG.md` 或 `UPDATELOG.md`
* 存放于产品根目录下
* 倒序排列各版本（新版本在上，旧版本在下）
* 各版本之间空三个空行
* 各版本格式为
    ```markdown
    # Version(tag) - yyyy-mm-dd

    type1
      subject
      ...

    type2
      subject
      ...

    ...
    ```
* 含有重大隐患的版本，应在版本后标注 `[YANKED]`
    例：`# 1.0.0 - 2024-07-16 [YANKED]`

### type

Added
: 新添加的功能。

Changed
: 对现有功能的变更。

Deprecated
: 已经不建议使用，准备很快移除的功能。

Removed
: 已经移除的功能。

Fixed
: 对bug的修复

Security
: 对安全的改进

## 代码风格约定（根据 https://zhuanlan.zhihu.com/p/134433380 整理改写）

### 一般排版约定

* 程序采用缩进风格，每层缩进使用一个制表位（TAB）
* 源程序使用英文书写，尽量不含有中文（除注释和界面文字）
* 左花括号要另起一行，尽可能不跟在上一行的行末
* 一个变量定义占一行，一个语句占一行
* 对独立的程序块之间、变量说明之后必须加空行
* 运算符两侧留空格
* 在+、-、*、/、!=等运算符的两侧应用空格隔开
* 代码块的注释都写在代码的上面
* 方法间要换行，同一个方法里不同的逻辑块也要换行
* 单行代码过长应当换行（除 Python），换行后的代码应增加一级缩进
    例如：
    ```basic
        MoveWindow hWndTabMain, _
            (picSplitter1.Visible And 1) * (picSplitter1.Left + picSplitter1.Width), _
            rbMain.rcClientRect.Bottom, _
            Me.ScaleWidth - ((picSplitter1.Visible And 1) * (picSplitter1.Left + picSplitter1.Width)), _
            (((Not picSplitter2.Visible) And 1) * (Me.ScaleHeight - staStatus.rcClientRect.Bottom)) + ((picSplitter2.Visible And 1) * picSplitter2.Top) - rbMain.rcClientRect.Bottom, _
            False
        
        UpdateControlRect tabMain
    ```
* 连续多行赋值代码，保持“=”整齐

### 命名约定

* 一般情况下，变量名应有意义，除了用于循环的 `i` 等
* 用小驼峰法或匈牙利命名法命名变量
    在 Windows 下编程，如果要使用大量 API 函数，应当使用匈牙利命名法
    例如：`hWndWindow` `lpszClassName`
    如果要对内存进行精细操作，应当使用匈牙利命名法，且类型前缀应当能明确指出变量实际大小
    例如：`dwHandle` `qwMask`
    其他情况下，应当使用小驼峰法命名
    例如：`userName` `objectCount`
* 常量与定义数据的宏一般全部大写，逻辑断点使用 `_` 连结
    例如：`MAX_FILM_COUNT` `SYSTEM_VERSION`
* 系统级编程时，内部常量、变量或定义数据的宏应以 `_` 或 `__` 起始
    例如：`__sysName` `_sysType`
* 对于函数，应当使用大驼峰法命名，一般以动词原型（除了 is 等）起始
    例如：`CreateObject` `IsNumber`

### 注释约定

* 文件注释应当包括 `创建日期时间` `创建人` `最后更新日期时间` `简介`
    例如：
    ```c
    // ---------------------------------------------------------------------------------------------
    // QISO
    // Version 0.0.1 Alpha
    // ---------------------------------------------------------------------------------------------
    // Copyright 2024 QZhi Studio
    //
    // Licensed under the Apache License, Version 2.0 (the "License");
    // you may not use this file except in compliance with the License.
    // You may obtain a copy of the License at
    //
    //     http://www.apache.org/licenses/LICENSE-2.0
    //
    // Unless required by applicable law or agreed to in writing, software
    // distributed under the License is distributed on an "AS IS" BASIS,
    // WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    // See the License for the specific language governing permissions and
    // limitations under the License.
    // ---------------------------------------------------------------------------------------------
    // 创建日期时间：2024-07-16 14:00
    // 创建人：QZhi
    // 最后更新日期时间：2024-07-16 14:30
    // ---------------------------------------------------------------------------------------------
    // 简述：
    // 此模块包含对 CDFS 的定义和相关内容。
    // ---------------------------------------------------------------------------------------------
    // 参考：
    // https://www.ecma-international.org/publications-and-standards/standards/ecma-119/
    // https://wiki.osdev.org/ISO_9660
    // http://cdfs.com/index-cdfs.html
    // https://www.0xaa55.com/thread-27326-1-1.html
    // https://www.drdobbs.com/database/inside-the-iso-9660-filesystem-format/184408899?pgno=1
    // https://pkg.go.dev/github.com/hooklift/iso9660
    // ---------------------------------------------------------------------------------------------
    ```
* 函数注释应当包括 `创建日期时间` `创建人` `作用` `返回值解析` `参数解析`
    例如：
    ```basic
    ' ******************************************************
    ' 创建日期时间：1998-06-01 00:00
    ' 创建人：Microsoft
    ' 目的：在用户列表数组中找出
    '      一个指定用户的第一次出现位置。
    ' 输入：
    '   strUserList()：    被搜索的用户列表。
    '   strTargetUser：    要搜索的用户名。
    ' 返回：在 rasUserList 数组中 rsTargetUser
    '       的第一次出现的索引。
    '       如果目标用户没找到，返回 -1。
    ' ******************************************************
    Function intFindUser(strUserList() As String, strTargetUser As _
        String) As Integer
        
        Dim i As Integer            ' 循环计数器。
        Dim blnFound As Integer     ' 目标寻找标志。

        intFindUser = -1
        i = 0

        While i <= Ubound(strUserList) and Not blnFound
            If strUserList(i) = strTargetUser Then
                blnFound = True
                intFindUser = i
                Exit Function
            End If
        Wend
        
    End Function
    ```