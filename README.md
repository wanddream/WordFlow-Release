# WordFlow 语音输入工具

中文语音识别工具，将语音实时转换为文字并输入到任意应用程序。

---

## 🚀 快速开始

### 三步安装法

1. **下载安装器** → 点击下载 [WordFlowInstaller.exe](https://gitee.com/cheng-yanlin/WordFlow-Release/releases/download/v1.0.0/WordFlowInstaller.exe) (8.5KB)
2. **运行安装器** → 自动下载主程序和模型
3. **开始使用** → 安装完成后即可使用语音输入

> **无需安装.NET运行时** - 主程序已包含所有依赖，开箱即用

---

## 📦 发布文件说明

### 用户只需下载的文件
| 文件 | 大小 | 说明 |
|------|------|------|
| [WordFlowInstaller.exe](https://gitee.com/cheng-yanlin/WordFlow-Release/releases/download/v1.0.0/WordFlowInstaller.exe) | 8.5KB | **超轻量安装器** - 自动下载所有必需文件 |

### 安装器自动下载的文件
| 文件 | 大小 | 说明 |
|------|------|------|
| WordFlow.zip | 71.64MB | **完整软件包** - 包含主程序+运行时+PythonASR |
| paraformer-zh.tar.bz2.part1 | 90MB | **模型第一部分** - 中文Paraformer模型 |
| paraformer-zh.tar.bz2.part2 | 90MB | **模型第二部分** - 中文Paraformer模型 |
| paraformer-zh.tar.bz2.part3 | 26MB | **模型第三部分** - 中文Paraformer模型 |

> **注意**：您只需下载8.5KB的安装器，软件包和模型将由安装器自动下载、合并并安装。

---

## 📋 系统要求

- **操作系统**: Windows 10/11 (64位)
- **硬件**: 4GB RAM, 500MB 可用磁盘空间
- **音频**: 麦克风设备
- **网络**: 安装时需要网络连接以下载主程序和模型

---

## 🔧 安装步骤

### 方法一：自动安装（推荐）

1. **下载安装器**
   - 点击 [WordFlowInstaller.exe](https://gitee.com/cheng-yanlin/WordFlow-Release/releases/download/v1.0.0/WordFlowInstaller.exe)
   - 保存到任意位置（如桌面）

2. **运行安装器**
   - 双击运行 `WordFlowInstaller.exe`
   - 选择安装位置（如：C:\Program Files\WordFlow）
   - 安装器会自动：
     - 下载 WordFlow.zip (71.64MB)
     - 下载 3个模型部分文件 (90MB+90MB+26MB)
     - 自动合并模型文件为完整文件
     - 自动解压WordFlow.zip到安装目录
     - 自动将合并后的模型文件放置到 `PythonASR\models\` 目录
     - 创建桌面快捷方式

3. **完成安装**
   - 等待下载完成（取决于网络速度）
   - 安装完成后自动提示
   - 双击桌面快捷方式启动WordFlow

### 方法二：手动安装（高级用户）

1. 分别下载四个文件：
   - [WordFlow.zip](https://gitee.com/cheng-yanlin/WordFlow-Release/releases/download/v1.0.0/WordFlow.zip)
   - [paraformer-zh.tar.bz2.part1](https://gitee.com/cheng-yanlin/WordFlow-Release/releases/download/v1.0.0/paraformer-zh.tar.bz2.part1)
   - [paraformer-zh.tar.bz2.part2](https://gitee.com/cheng-yanlin/WordFlow-Release/releases/download/v1.0.0/paraformer-zh.tar.bz2.part2)
   - [paraformer-zh.tar.bz2.part3](https://gitee.com/cheng-yanlin/WordFlow-Release/releases/download/v1.0.0/paraformer-zh.tar.bz2.part3)
2. 解压 WordFlow.zip 到目标目录
3. 将3个part文件复制到 `目标目录\PythonASR\models\`
4. 使用命令行合并part文件：
   ```
   cd 目标目录\PythonASR\models
   copy /b paraformer-zh.tar.bz2.part1 + paraformer-zh.tar.bz2.part2 + paraformer-zh.tar.bz2.part3 paraformer-zh.tar.bz2
   ```
5. 运行 WordFlow.exe

---

## 🎯 使用方法

### 首次使用设置

1. **启动程序**
   - 双击桌面快捷方式或运行 `WordFlow.exe`
   - 程序启动后最小化到系统托盘

2. **配置热键**
   - 右键托盘图标 → 设置
   - 选择录音热键（默认：Caps Lock）
   - 保存设置

3. **开始语音输入**
   - 将光标定位到要输入文字的窗口
   - **按住**热键开始录音
   - **松开**热键结束录音并识别
   - 识别结果自动输入到当前窗口

### 快速操作指南

| 操作 | 快捷键/方法 | 说明 |
|------|-------------|------|
| 启动程序 | 双击桌面图标 | 启动后最小化到托盘 |
| 开始录音 | **按住** Caps Lock | 默认热键，可在设置中更改 |
| 结束录音 | **松开** Caps Lock | 自动识别并输入文字 |
| 打开设置 | 右键托盘图标 → 设置 | 配置热键、开机启动等 |
| 显示主窗口 | 右键托盘图标 → 显示主窗口 | 查看历史记录和词典 |
| 退出程序 | 右键托盘图标 → 退出 | 完全关闭程序 |

### 托盘图标状态说明

| 图标状态 | 含义 | 建议操作 |
|----------|------|----------|
| 🟢 绿色 | 服务正常，准备就绪 | 可开始语音输入 |
| 🔴 红色 | 服务异常 | 检查麦克风连接或重启程序 |
| ⚪ 灰色 | 程序未运行 | 启动 WordFlow.exe |

**右键托盘图标菜单功能**：
- 📋 显示主窗口 - 打开主界面查看历史记录
- ⚙️ 打开设置 - 配置热键、开机启动等选项
- 🔄 开机自启动 - 设置程序开机自动启动
- ❌ 退出 - 完全关闭程序

---

## 常见问题

### 安装问题

**Q: 安装时提示"无法写入文件"**
- 关闭杀毒软件后重试
- 以管理员权限运行安装程序
- 更换安装路径（避免中文或特殊字符）

**Q: 安装后无法启动**
- 检查是否被杀毒软件拦截
- 确认安装路径不含中文字符
- 右键选择"以管理员身份运行"

### 模型下载问题

**Q: 模型下载失败或速度慢**
- 检查网络连接
- 手动下载3个part文件到 `安装目录\PythonASR\models\` 文件夹
- 下载地址：
  - https://gitee.com/cheng-yanlin/WordFlow-Release/releases/download/v1.0.0/paraformer-zh.tar.bz2.part1
  - https://gitee.com/cheng-yanlin/WordFlow-Release/releases/download/v1.0.0/paraformer-zh.tar.bz2.part2
  - https://gitee.com/cheng-yanlin/WordFlow-Release/releases/download/v1.0.0/paraformer-zh.tar.bz2.part3
- 手动合并命令：
  ```
  copy /b paraformer-zh.tar.bz2.part1 + paraformer-zh.tar.bz2.part2 + paraformer-zh.tar.bz2.part3 paraformer-zh.tar.bz2
  ```

**Q: 提示"模型文件损坏"**
- 删除 `PythonASR\models\` 目录后重新下载
- 确认磁盘空间充足（至少 500 MB）

### 语音识别问题

**Q: 按快捷键无反应**
- 确认托盘图标为绿色（服务正常）
- 检查麦克风是否被其他程序占用
- 尝试重启程序

**Q: 识别准确率低**
- 使用质量较好的麦克风
- 在安静环境下使用
- 距离麦克风 10-30 cm

**Q: 识别后文字未输入到目标窗口**
- 确保目标窗口处于活动状态
- 确保光标在可输入区域闪烁
- 以管理员权限运行 WordFlow
- 关闭 UAC 虚拟化（任务管理器 → 详细信息 → 右键 WordFlow → 取消 UAC 虚拟化）

### 快捷键问题

**Q: 快捷键冲突**
- 进入设置更换快捷键
- 常见冲突：输入法切换、其他语音软件

**Q: Caps Lock 失效**
- WordFlow 默认拦截 Caps Lock 用于语音输入
- 可在设置中更改或禁用此行为

---

## 技术架构

| 组件 | 技术 |
|------|------|
| 前端界面 | WPF (.NET 8) |
| 语音识别 | FunASR + ONNX Runtime |
| 后端服务 | Python Flask |

---

## 许可证

本软件供个人非商业使用。

---

## 反馈与支持

遇到问题或有建议，请在 Gitee Issues 页面反馈。
