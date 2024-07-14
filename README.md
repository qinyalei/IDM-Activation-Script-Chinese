# IDM 激活脚本
一个用于激活和重置 [Internet Download Manager](https://www.internetdownloadmanager.com/) 试用期的开源工具。

# 声明
我想澄清一下，我不是这个脚本的原始作者。当我最初在 GitHub 上发布这个脚本时，主要作者还没有创建官方的 GitHub 仓库。因此，用户唯一的选择是访问[官方论坛](https://www.nsaneforums.com/topic/371047--/?do=findComment%5E&comment=1578647)来下载和使用脚本，后来他们创建了 [Github](https://github.com/WindowsAddict/IDM-Activation-Script) 仓库。我创建这个仓库的主要目的是为了简化用户的流程。此外，我确保对脚本的原始作者进行了信用，以尊重他们的工作。

# 特点
* 使用注册表键锁定方法冻结 IDM 试用期和激活
* 完全开源
* 基于透明的批处理脚本

# IAS 最新版本
最新版本 - v1.2 (2024年2月12日)
[GitHub](https://github.com/lstprjct/IDM-Activation-Script)

# 下载 / 如何使用？
首先，全新安装 [Internet Download Manager](https://www.internetdownloadmanager.com/)。确保删除/卸载以前的破解/补丁（如果有的话）。
然后按照下面的步骤激活它。

# 注意
* 📌 脚本中的激活选项目前不起作用，请使用冻结试用选项将 30 天试用期永久锁定。

# 方法 1 - PowerShell
(推荐)

* 右键单击 Windows 开始菜单，选择 PowerShell 或终端（不是 CMD）。
* 复制以下代码并按 Enter 键
* `iex(irm is.gd/idm_reset)`
* 您将看到激活选项，请按照屏幕上的说明操作。
* 就这样。

# 方法 2 - 传统方法

* 从 [GitHub](https://github.com/lstprjct/IDM-Activation-Script/archive/refs/heads/main.zip) 下载文件
* 右键单击下载的 zip 文件并解压缩
* 在解压后的文件夹中，运行名为 `IAS.cmd` 的文件
* 您将看到激活选项，并按照屏幕上的说明操作。
* 就这样。

# 信息
## 冻结试用
* IDM 提供 30 天的试用期，您可以在脚本中使用此选项将此试用期永久锁定，这样您就不必再次重置试用期，也不会过期。
* 此方法在应用此选项时需要互联网连接。
* 可以直接安装 IDM 更新，无需再次冻结。

## 激活
(***目前不起作用***)

* 此脚本应用注册表锁定方法激活 Internet Download Manager（IDM）。
* 此方法在激活时需要互联网连接。
* 可以直接安装 IDM 更新，无需再次激活。
* 在激活后，如果在某些情况下 IDM 开始显示激活提示窗口，则只需再次运行激活选项，而不使用重置选项。

## 重置 IDM 激活 / 试用
* Internet Download Manager 提供 30 天的试用期，您可以使用此脚本在需要时重置此激活 / 试用期。
* 如果 IDM 报告假序列密钥和其他类似错误，也可以使用此选项来恢复状态。

## 操作系统要求
* 该项目支持 Windows 7/8/8.1/10/11 及其服务器等效版本。
* 在 Windows 8 及更高版本上支持使用 PowerShell 运行 IAS 的方法。

## 高级信息
* 要以无人值守模式激活，请使用 /act 参数运行脚本。
* 要以无人值守模式冻结试用，请使用 /frz 参数运行脚本。
* 要以无人值守模式重置，请使用 /res 参数运行脚本。

# 工作原理
* IDM 在各种注册表键中存储与试用和激活相关的数据。其中一些键被锁定以防止篡改，并且数据以一种模式存储，以跟踪假序列问题和剩余的试用天数。为了激活它，此处的脚本简单地通过在 IDM 中触发几次下载来生成这些注册表键，识别这些注册表键，并将它们锁定，以便 IDM 无法编辑和查看它们。这样 IDM 就不会显示使用假序列密钥激活的警告。

# 故障排除
* 浏览器集成修复：[Chrome](https://www.internetdownloadmanager.com/register/new_faq/bi9.html) - [Firefox](https://www.internetdownloadmanager.com/register/new_faq/bi4.html)
* 通过 [Telegram](https://t.me/ModByPiash) 向我们发送错误截图。
[![](https://upload.wikimedia.org/wikipedia/commons/thumb/8/82/Telegram_logo.svg/512px-Telegram_logo.svg.png)](https://t.me/ModByPiash)

# 更改日志
## v1.2
* 添加了激活选项，使用随机名称、电子邮件和注册详情中的密钥，同时警告说对于一些用户来说这不起作用，推荐使用冻结试用选项。
## v1.1
* IDM 更新 6.42b3 开始显示假序列弹出窗口与 IAS 激活，因此我们已删除激活选项，并更换为冻结试用选项以永久锁定 30 天的试用期。
* 现在脚本将使用 Powershell 禁用 CMD 窗口的快速编辑，而不是编辑注册表，感谢 @abbodi1406 提供的代码和 @awuctl 的想法。
* 代码以使用 conhost.exe 重新启动脚本以避免终端应用程序的方式现在合并在快速编辑禁用代码中，感谢 @abbodi1406。
从 [WindowsAddict](https://massgrave.dev/idm-activation-script) 更新了完整代码。
## v1.0
* 添加了使用 conhost.exe 重新启动脚本的代码，如果脚本是从终端应用程序运行的。
* 修复了获取当前用户帐户 SID 的问题。
## v0.9
* 修复了脚本无法在非管理员用户帐户中激活和重置 IDM 的问题。
* 修复了脚本错误地显示 IDM 已激活的问题。
* 修复了可能出现假序列弹出窗口的问题。脚本还将显示运行激活选项的信息，而不使用重置选项。
* IDM 注册表扫描和锁定代码现在使用 Powershell 编写。
* 脚本更新检查器代码已添加到脚本中。
* 脚本现在将临时禁用快速编辑模式，因为用户经常在脚本窗口中单击，这会使脚本暂停。
* 脚本将在执行操作之前备份 CLSISD 注册表键。
* 添加了许多错误检查以更好地识别问题。
## v0.8
* 将项目迁移到 [Github](https://github.com/lstprjct/IDM-Activation-Script)
* 修复了一些小错误
* 添加了信息以通知用户在脚本删除大量空注册表键时正在删除这些键。

# 截图
![IAS](https://github.com/lstprjct/IDM-Activation-Script/assets/88411318/fafdb481-c497-464f-b1e6-9a4254eaf880)

![IAS_Freeze_Trial](https://github.com/lstprjct/IDM-Activation-Script/assets/88411318/76b36582-8cf4-4d1e-870f-6e8e57c80a87)

# 鸣谢

|                                             |                                                                                                                                                                                                                                        |
|-------------------|-----------------------------------------------------|
| Dukun Cabul                                 | 此 IDM 试用期重置和激活逻辑的原始研究人员，为这些方法制作了一个 Autoit 工具，[IDM-AIO_2020_Final](https://nsaneforums.com/topic/371047-discussion-internet-download-manager-fixes/page/8/#comment-1632062) |
| AveYo aka BAU                               | [reg_own 简洁而有效的片段](https://pastebin.com/XTPt0JSC)                                                                                                                                                                       |
| [abbodi1406](https://github.com/abbodi1406) | 在编码方面提供帮助                                                                                                                                                                                                              |
| WindowsAddict                               | 原始 [IAS](https://github.com/WindowsAddict/IDM-Activation-Script) 作者                                                                                                                                                                                                      |

感谢 IAS 用户的关注、反馈和协助。

------------------------------------------------------------------------

用爱心制作 ❤️
